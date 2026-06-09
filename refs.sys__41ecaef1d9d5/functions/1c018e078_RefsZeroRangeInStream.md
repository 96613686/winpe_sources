# RefsZeroRangeInStream

- ea: `0x1c018e078`
- end: `0x1c018f51c`
- name: `RefsZeroRangeInStream`
- size: `5284`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c01bd6c0`

## callees

- `0x1c0001268`
- `0x1c0001d74`
- `0x1c0004300`
- `0x1c000440c`
- `0x1c0005768`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c003aa60`
- `0x1c003b27c`
- `0x1c004d164`
- `0x1c00583d0`
- `0x1c005bb10`
- `0x1c005c650`
- `0x1c005f020`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c006af80`
- `0x1c0090d50`
- `0x1c0091258`
- `0x1c009166c`
- `0x1c0091864`
- `0x1c00925e8`
- `0x1c009263c`
- `0x1c00a29c4`
- `0x1c00adb9c`
- `0x1c014fe2c`
- `0x1c0151130`
- `0x1c015ac58`
- `0x1c01632d4`
- `0x1c01634c8`
- `0x1c016a350`
- `0x1c018c374`
- `0x1c018c5dc`
- `0x1c018cf2c`
- `0x1c018e078`
- `0x1c018f6fc`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c018e18f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f1b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f2c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f35f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f468`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f506`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018e18f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f1b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f2c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f35f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f468`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f506`
- `ntoskrnl!CcFlushCache` at `0x1c018ef83`
- `ntoskrnl!CcFlushCache` at `0x1c018ef83`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c018ee48`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c018eecf`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c018ee48`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c018eecf`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c018ea90`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c018ecd6`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c018ea90`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1c018ecd6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c018eaca`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c018ed0f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c018eaca`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c018ed0f`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018eb70`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018edb9`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018f3ab`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018f3e9`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018eb70`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018edb9`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018f3ab`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018f3e9`

## pseudocode

```c
__int64 __fastcall RefsZeroRangeInStream(LONGLONG a1, __int64 a2, __int64 a3, int *a4, LONGLONG a5)
{
  int *v5; // r15
  __int64 v7; // r13
  LONGLONG v8; // r14
  LONGLONG v9; // r12
  __int64 v10; // r8
  int valid; // esi
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rcx
  int v17; // eax
  LONGLONG v18; // rcx
  LONGLONG v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  NTSTATUS v22; // eax
  int v23; // edx
  int v24; // r8d
  __int64 v25; // r11
  LONGLONG v26; // r9
  __int64 v27; // r15
  LONGLONG v28; // rax
  unsigned int v29; // edx
  int v30; // eax
  signed __int64 v31; // r13
  __int64 v32; // rcx
  __int64 v33; // r15
  int v34; // r13d
  char v35; // al
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rax
  char v39; // cl
  unsigned __int64 v40; // r15
  __int64 v41; // r13
  unsigned __int64 v42; // r15
  union _LARGE_INTEGER v43; // rax
  int *v44; // r10
  __int64 v45; // rcx
  unsigned int v46; // r13d
  __int64 v47; // rdx
  LONGLONG v48; // r15
  int *v49; // r13
  unsigned int v50; // r13d
  PVOID v51; // rax
  unsigned int v52; // ecx
  unsigned int v53; // r15d
  LONGLONG v54; // r13
  PVOID MappedSystemVa; // rax
  __int64 v56; // r12
  __int64 v57; // r12
  SECTION_OBJECT_POINTERS *v58; // rcx
  int v59; // edx
  __int64 v60; // r12
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rdx
  unsigned int v64; // eax
  ULONG Priority[2]; // [rsp+28h] [rbp-160h]
  int v67; // [rsp+30h] [rbp-158h]
  int v68; // [rsp+38h] [rbp-150h]
  char v69; // [rsp+70h] [rbp-118h]
  NTSTATUS Status; // [rsp+74h] [rbp-114h] BYREF
  char v71; // [rsp+78h] [rbp-110h] BYREF
  char v72; // [rsp+79h] [rbp-10Fh] BYREF
  char v73[6]; // [rsp+7Ah] [rbp-10Eh] BYREF
  union _LARGE_INTEGER v74; // [rsp+80h] [rbp-108h] BYREF
  __int64 v75; // [rsp+88h] [rbp-100h]
  char v76[8]; // [rsp+90h] [rbp-F8h] BYREF
  PMDL MdlChain; // [rsp+98h] [rbp-F0h] BYREF
  unsigned int v78; // [rsp+A0h] [rbp-E8h]
  int v79; // [rsp+A4h] [rbp-E4h]
  int v80; // [rsp+A8h] [rbp-E0h]
  __int64 v81; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-D0h]
  union _LARGE_INTEGER FileOffset; // [rsp+C0h] [rbp-C8h] BYREF
  LONGLONG v84; // [rsp+C8h] [rbp-C0h]
  union _LARGE_INTEGER v85; // [rsp+D0h] [rbp-B8h]
  int v86; // [rsp+D8h] [rbp-B0h]
  __int64 v87; // [rsp+E0h] [rbp-A8h]
  LONGLONG v88; // [rsp+E8h] [rbp-A0h]
  __int64 v89; // [rsp+F0h] [rbp-98h]
  __int128 v90; // [rsp+100h] [rbp-88h]
  __int128 v91; // [rsp+110h] [rbp-78h] BYREF
  __int64 v92; // [rsp+120h] [rbp-68h] BYREF
  __int64 v93; // [rsp+128h] [rbp-60h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+130h] [rbp-58h] BYREF
  __int128 v95[4]; // [rsp+140h] [rbp-48h] BYREF
  int *v97; // [rsp+1A8h] [rbp+20h]

  v97 = a4;
  v5 = a4;
  v7 = a2;
  v8 = a1;
  v9 = a5;
  v10 = 0;
  valid = 0;
  Status = 0;
  *(_QWORD *)&v90 = -1;
  v74.QuadPart = 0;
  v81 = 0;
  v85.QuadPart = 0;
  v84 = 0;
  v91 = 0;
  v79 = 0;
  v92 = 0;
  v71 = 0;
  v76[0] = 0;
  v72 = 0;
  MdlChain = 0;
  IoStatus = 0;
  v12 = 0;
  v69 = 0;
  while ( 1 )
  {
    if ( *(_QWORD *)(a3 + 16) )
    {
      if ( *(_QWORD *)(v8 + 56) )
        goto LABEL_16;
      if ( (v12 & 4) != 0 || *(_QWORD *)(*(_QWORD *)(a3 + 240) + 8LL) || (*(_DWORD *)(a3 + 136) & 0x28) != 0x20 )
      {
        LOBYTE(v10) = 1;
        RefsAcquirePagingResourceExclusive(a1, a3, v10);
        v13 = v12 & 0xFFFFFFF9 | 2;
      }
      else
      {
        LOBYTE(v10) = 1;
        RefsAcquirePagingResourceShared(a1, a3, v10);
        v13 = v12 & 0xFFFFFFFD;
        v10 = 0;
        if ( *(_QWORD *)(*(_QWORD *)(a3 + 240) + 8LL) || (*(_DWORD *)(a3 + 136) & 0x28) != 0x20 )
        {
          v14 = a3;
          if ( *(_WORD *)a3 != 2050 )
            v14 = *(_QWORD *)(a3 + 120);
          ExReleaseResourceLite(*(PERESOURCE *)(v14 + 104));
          LOBYTE(v15) = 1;
          RefsAcquirePagingResourceExclusive(v16, a3, v15);
          v13 |= 2u;
        }
      }
      v12 = v13 | 1;
    }
    else
    {
      RefsAcquireExclusiveScbWithFlags(v8, a3, 0);
      v12 |= 8u;
    }
    v69 = v12;
LABEL_16:
    v17 = *(_DWORD *)(a3 + 304);
    if ( (v17 & 0x40) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741533;
      }
      else
      {
        valid = -1073741533;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids, 3221225763LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_24;
      goto LABEL_23;
    }
    if ( (v17 & 0x10000) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741202;
      }
      else
      {
        valid = -1073741202;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids, 3221226094LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_24;
LABEL_23:
      RefsStatusDebug(valid);
LABEL_24:
      Status = valid;
      LOBYTE(v12) = v69;
      goto LABEL_233;
    }
    if ( !(unsigned __int8)RefsIsFileOpen(*(_QWORD *)(a3 + 120), a2, v10) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        valid = -1073741528;
      }
      else
      {
        valid = -1073741528;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids, 3221225768LL);
      }
      if ( RefsStatusDebugEnabled )
        goto LABEL_40;
LABEL_41:
      Status = valid;
      LOBYTE(v12) = v69;
      goto LABEL_233;
    }
    if ( (*(_DWORD *)(a3 + 136) & 0x20) == 0 )
      RefsUpdateScbFromAttribute(v8, a3, 0);
    v18 = *(_QWORD *)v5;
    v19 = *(_QWORD *)(a3 + 32);
    if ( *(_QWORD *)v5 >= v19 || v18 >= v9 )
      goto LABEL_72;
    if ( v7 )
    {
      v20 = v9 - v18;
      v75 = v9 - v18;
      v21 = v9 - v18;
      if ( v9 > v19 )
      {
        v20 = v19 - v18;
        v75 = v19 - v18;
        v21 = v19 - v18;
      }
      if ( v21 > 0x40000000 )
        v20 = 0x40000000;
      v75 = v20;
      v22 = RefsCheckLocksInZeroRange((PVOID)v8, *(PIRP *)(v8 + 72), (__int64)v5, v20);
      valid = v22;
      Status = v22;
      if ( v22 )
      {
        if ( v22 != 264 )
          goto LABEL_233;
      }
    }
    RefsPostUsnChangeWithOverrideOption(v8, a3, 1);
    v25 = 0;
    if ( v7 )
      *(_DWORD *)(v7 + 80) |= 0x1000u;
    if ( (*(_DWORD *)(a3 + 136) & 8) != 0 )
      break;
    if ( *(__int16 *)(a3 + 252) >= 0 )
    {
      v12 &= ~0x10u;
      v69 = v12;
      v29 = *(_DWORD *)(*(_QWORD *)(a3 + 128) + 272LL);
      v30 = 1;
    }
    else
    {
      v12 |= 0x10u;
      v69 = v12;
      v29 = *(_DWORD *)(a3 + 248);
      v30 = 1 << *(_BYTE *)(a3 + 254);
    }
    LODWORD(v82) = v30;
    v78 = v29;
    v80 = (v12 >> 4) & 1;
    if ( !v80 && *(_WORD *)a3 == 2053 && *(_QWORD *)(a3 + 360) && *(_WORD *)(a3 + 258) && v8 == *(_QWORD *)(v8 + 104) )
      *(_DWORD *)(v8 + 8) |= 8u;
    v31 = *(_QWORD *)v5 & ~(unsigned __int64)(v29 - 1);
    v74.QuadPart = v31;
    v88 = v9;
    v32 = *(_QWORD *)(a3 + 32);
    if ( a5 >= v32 )
    {
      v9 = -v29 & (unsigned __int64)(v32 + (int)(v29 - 1));
      v88 = v9;
    }
    v89 = v31 >> *(_BYTE *)(*(_QWORD *)(a3 + 128) + 464LL);
    v93 = v89;
    v33 = v89;
    v87 = v89;
    v34 = v80;
    while ( 1 )
    {
      v35 = RefsLookupAllocationEx(
              v8,
              a3,
              v33,
              4,
              (__int64)&v92,
              (__int64)&v81,
              v67,
              v68,
              v25,
              (__int64)&v71,
              (__int64)v76,
              (__int64)&v72,
              0x40000);
      v25 = 0;
      if ( v35 || v72 || v34 && v71 )
        break;
      if ( *(__int16 *)(a3 + 252) >= 0 && !v71 )
      {
        v12 = RefsQueueTriageForDeadFcb(v8, *(_QWORD *)(a3 + 120), v36, v37);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qd(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids,
            *(_QWORD *)(a3 + 120),
            v12);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(v12);
        RefsRaiseStatusInternal(v8, v12);
      }
      v33 += v81;
      v87 = v33;
      v38 = *(_QWORD *)(a3 + 128);
      v39 = *(_BYTE *)(v38 + 464);
      if ( v33 >= (v9 + *(unsigned int *)(v38 + 456)) >> v39 )
      {
        v33 = v9 >> v39;
        v87 = v9 >> v39;
        break;
      }
    }
    RefsCheckpointCurrentTransaction(v8);
    v40 = -(int)v82 & (unsigned __int64)v33;
    v82 = v40;
    v87 = v40;
    v41 = v89;
    if ( v40 != v89 )
    {
      v42 = v40 - v89;
      v81 = v42;
      if ( *(_QWORD *)(*(_QWORD *)(a3 + 240) + 8LL) && v80 )
      {
        RefsCheckForReservedClusters(a3, v89, &v81);
        v42 = v81;
      }
      v41 += v42;
      v89 = v41;
      v93 = v41;
    }
    v43.QuadPart = v41 << *(_BYTE *)(*(_QWORD *)(a3 + 128) + 464LL);
    v74 = v43;
    if ( v43.QuadPart >= v9 )
    {
      *(_QWORD *)v97 = v9;
      v7 = a2;
      goto LABEL_72;
    }
    v44 = v97;
    v45 = *(_QWORD *)v97;
    if ( v43.QuadPart >= *(_QWORD *)v97 )
    {
      v53 = v78;
      v54 = v78;
      if ( v43.QuadPart + v78 > v9 )
      {
        if ( (v12 & 0x10) != 0
          && !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RefsReserveClusters)(
                                 v8,
                                 a3,
                                 (union _LARGE_INTEGER)v74.QuadPart,
                                 v78) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            valid = -1073741697;
          }
          else
          {
            valid = -1073741697;
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids,
              3221225599LL);
          }
          if ( !RefsStatusDebugEnabled )
            goto LABEL_41;
          goto LABEL_40;
        }
        v48 = (unsigned int)v9 & (v53 - 1);
        v75 = v48;
        if ( !*(_QWORD *)(a3 + 224) )
        {
          if ( (v12 & 3) == 1 )
          {
LABEL_130:
            v12 |= 4u;
            v69 = v12;
            v48 = 0;
            v75 = 0;
            v86 = ++v79;
LABEL_131:
            v49 = v97;
            goto LABEL_132;
          }
          RefsCreateInternalAttributeStream(v8, a3, 0, L"(*");
        }
        if ( v48 )
        {
          MdlChain = 0;
          CcPrepareMdlWrite(*(PFILE_OBJECT *)(a3 + 224), &v74, v48, &MdlChain, &IoStatus);
          if ( (MdlChain->MdlFlags & 5) != 0 )
            MappedSystemVa = MdlChain->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
          if ( !MappedSystemVa )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                36,
                WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids,
                3221225626LL);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741670);
            MappedSystemVa = (PVOID)RefsRaiseStatusInternal(v8, 3221225626LL);
          }
          memset(MappedSystemVa, 0, (unsigned int)v48);
          if ( MdlChain )
            CcMdlWriteComplete(*(PFILE_OBJECT *)(a3 + 224), &v74, MdlChain);
        }
        goto LABEL_131;
      }
      v56 = v9 - v43.QuadPart;
      v75 = v56;
      if ( v56 > 0x40000000 )
      {
        v75 = 0x40000000;
        v56 = 0x40000000;
      }
      v48 = v56 & -v78;
      v75 = v48;
      v57 = v48;
      if ( v45 == (_QWORD)v90 && v48 > v78 )
      {
        v48 = v78;
        v75 = v78;
        v88 = v43.QuadPart + v78;
        v57 = v78;
      }
      v58 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(a3 + 240) + 8LL);
      if ( v58->DataSectionObject )
      {
        if ( CcPurgeCacheSection(v58, &v74, v48, 0) )
        {
          CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 240) + 8LL), &v74, v48, 0);
        }
        else
        {
          valid = RefsCacheCoherencyFlush(v8, v59, a3, v74.LowPart, v48, 1, 0);
          Status = valid;
          if ( valid == -1073740747 )
          {
            if ( v57 > v54 )
            {
              v48 = v54;
              v75 = v54;
              v88 = v54 + v74.QuadPart;
              v57 = v54;
            }
            v49 = v97;
            if ( !CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 240) + 8LL), &v74, v48, 0) )
            {
              if ( *(_QWORD *)v97 == (_QWORD)v90 )
              {
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                {
                  valid = -1073741797;
                }
                else
                {
                  valid = -1073741797;
                  WPP_SF_D(
                    WPP_GLOBAL_Control->AttachedDevice,
                    37,
                    WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids,
                    3221225499LL);
                }
                if ( !RefsStatusDebugEnabled )
                  goto LABEL_41;
LABEL_40:
                RefsStatusDebug(valid);
                goto LABEL_41;
              }
              v48 = 0;
              v75 = 0;
              v57 = 0;
            }
LABEL_199:
            if ( v57 )
            {
              if ( (v12 & 8) == 0 )
              {
                if ( (v12 & 2) == 0 )
                {
                  v85 = v74;
                  v84 = v48;
                  RefsAcquireRangeLock(v8, *(_QWORD *)(a3 + 240), v74.LowPart, v48, 1, (__int64)&v91);
                  v12 |= 0x20u;
                }
                RefsCheckpointCurrentTransaction(v8);
                RefsAcquireExclusiveScbWithFlags(v8, a3, 0);
                v12 |= 8u;
                v69 = v12;
              }
              v60 = v57 >> *(_BYTE *)(*(_QWORD *)(a3 + 128) + 464LL);
              v81 = v60 + v89 - 1;
              if ( (v12 & 0x10) != 0 )
              {
                if ( v82 <= v60 + v89 - 1 )
                {
                  RefsDeleteAllocation(v8, a2, a3, v82, v60 + v89 - 1, *(_WORD *)(a3 + 252) >= 0);
                  RefsCheckpointCurrentTransaction(v8);
                }
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RefsFreeReservedClusters)(
                  v8,
                  a3,
                  (union _LARGE_INTEGER)v74.QuadPart,
                  (unsigned int)v48);
              }
              else
              {
                *(_QWORD *)&v90 = v82;
                *((_QWORD *)&v90 + 1) = v60 + v89 - v82;
                RefsBindMinstoreTransaction(v8);
                v95[0] = v90;
                valid = MsSetRangeValidState(*(_QWORD *)(v8 + 24), *(_QWORD *)(a3 + 360), v95, 0);
                Status = valid;
                if ( valid < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_D(
                      WPP_GLOBAL_Control->AttachedDevice,
                      38,
                      WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids,
                      (unsigned int)valid);
                  }
                  if ( RefsStatusDebugEnabled )
                    RefsStatusDebug(Status);
                  RefsRaiseStatusInternal(v8, (unsigned int)Status);
                  goto LABEL_216;
                }
              }
            }
            goto LABEL_132;
          }
        }
      }
      v49 = v97;
      goto LABEL_199;
    }
    FileOffset.QuadPart = 0;
    v46 = v78;
    if ( v80 )
    {
      if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RefsReserveClusters)(
                               v8,
                               a3,
                               (union _LARGE_INTEGER)v74.QuadPart,
                               v78) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          valid = -1073741697;
        }
        else
        {
          valid = -1073741697;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            33,
            WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids,
            3221225599LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_41;
        goto LABEL_40;
      }
      v44 = v97;
    }
    v47 = *(_QWORD *)v44;
    v48 = v74.QuadPart + v46 - *(_QWORD *)v44;
    v75 = v48;
    if ( v74.QuadPart + v46 > v9 )
    {
      v48 = v9 - v47;
      v75 = v9 - v47;
    }
    if ( !*(_QWORD *)(a3 + 224) )
    {
      if ( (v12 & 3) == 1 )
        goto LABEL_130;
      RefsCreateInternalAttributeStream(v8, a3, 0, L"&(");
      v44 = v97;
    }
    if ( !v48 )
      goto LABEL_131;
    v50 = v46 - 1;
    FileOffset.QuadPart = v74.QuadPart + (*v44 & v50);
    MdlChain = 0;
    CcPrepareMdlWrite(*(PFILE_OBJECT *)(a3 + 224), &FileOffset, v48, &MdlChain, &IoStatus);
    if ( (MdlChain->MdlFlags & 5) != 0 )
      v51 = MdlChain->MappedSystemVa;
    else
      v51 = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v51 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids, 3221225626LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741670);
      v51 = (PVOID)RefsRaiseStatusInternal(v8, 3221225626LL);
    }
    memset(v51, 0, (unsigned int)v48);
    if ( MdlChain )
      CcMdlWriteComplete(*(PFILE_OBJECT *)(a3 + 224), &FileOffset, MdlChain);
    v52 = v50;
    v49 = v97;
    v74.QuadPart += *v97 & v52;
LABEL_132:
    RefsCheckpointCurrentTransaction(v8);
    RefsFlushForWriteThrough(v8, a3);
    *(_QWORD *)&v90 = *(_QWORD *)v49;
    if ( v48 )
    {
      a1 = v74.QuadPart + v48;
      v5 = v97;
      *(_QWORD *)v97 = a1;
      goto LABEL_217;
    }
LABEL_216:
    v5 = v97;
LABEL_217:
    if ( (v12 & 0x20) != 0 )
    {
      LOBYTE(a4) = 1;
      RefsReleaseRangeLock(*(_QWORD *)(a3 + 240), v85.LowPart, v84, (_DWORD)a4, (__int64)&v91);
      v12 &= ~0x20u;
      v69 = v12;
    }
    if ( (v12 & 1) != 0 )
    {
      v61 = a3;
      if ( *(_WORD *)a3 != 2050 )
        v61 = *(_QWORD *)(a3 + 120);
      ExReleaseResourceLite(*(PERESOURCE *)(v61 + 104));
      v12 &= ~1u;
      v69 = v12;
    }
    if ( (v12 & 8) != 0 )
    {
      RefsReleaseFcb(v8, *(_QWORD *)(a3 + 120));
      v12 &= ~8u;
      v69 = v12;
    }
    v7 = a2;
    v9 = a5;
    v10 = 0;
  }
  v26 = *(_QWORD *)v5;
  v27 = v9 - *(_QWORD *)v5;
  v75 = v27;
  v28 = *(_QWORD *)(a3 + 32);
  if ( v9 > v28 )
  {
    v27 = v28 - v26;
    v75 = v28 - v26;
  }
  if ( !*(_QWORD *)(*(_QWORD *)(a3 + 240) + 8LL) )
    goto LABEL_69;
  valid = RefsCacheCoherencyFlush(v8, v23, a3, v26, v27, 1, 0);
  Status = valid;
  if ( valid == -1073740747 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      valid = -1073741797;
    }
    else
    {
      valid = -1073741797;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids, 3221225499LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741797);
    Status = -1073741797;
    v27 = v75;
    LOBYTE(v12) = v69;
  }
  if ( valid >= 0 )
  {
LABEL_69:
    if ( (v12 & 8) == 0 )
    {
      RefsAcquireExclusiveScbWithFlags(v8, a3, 0);
      LOBYTE(v12) = v12 | 8;
    }
    Priority[0] = v27;
    RefsResidentWrite(v8, 0, v24, a3, *v97, *(size_t *)Priority);
    RefsCheckpointCurrentTransaction(v8);
    *(_QWORD *)v97 += v27;
LABEL_72:
    if ( !valid && v7 && (*(_DWORD *)(v7 + 80) & 0x18) != 0 )
    {
      if ( *(_DWORD *)(a3 + 144) != *(_DWORD *)(a3 + 140) || *(_BYTE *)(a3 + 252) )
      {
        Status = RefsFlushUserStream(v8, a3);
        RefsNormalizeAndCleanupTransaction(v8, &Status);
        valid = Status;
      }
      else
      {
        if ( (v12 & 8) != 0 )
        {
          RefsReleaseFcb(v8, *(_QWORD *)(a3 + 120));
          LOBYTE(v12) = v12 & 0xF7;
        }
        RefsFlushAndPurgeScb(v8, a3);
      }
      if ( (v12 & 8) == 0 )
      {
        RefsAcquireExclusiveScbWithFlags(v8, a3, 0);
        LOBYTE(v12) = v12 | 8;
      }
      if ( (*(_DWORD *)(v7 + 80) & 0x10) != 0 )
      {
        v73[0] = 0;
        RefsHasPendingRedo(v8, a3, v73);
        if ( v73[0] )
          *(_DWORD *)(v8 + 8) |= 0x400u;
      }
      RefsFlushForWriteThrough(v8, a3);
    }
  }
LABEL_233:
  if ( (v12 & 0x20) != 0 )
  {
    LOBYTE(a4) = 1;
    RefsReleaseRangeLock(*(_QWORD *)(a3 + 240), v85.LowPart, v84, (_DWORD)a4, (__int64)&v91);
  }
  if ( valid == 259 )
  {
    if ( (v12 & 1) != 0 )
    {
      if ( *(_WORD *)a3 != 2050 )
        a3 = *(_QWORD *)(a3 + 120);
      ExReleaseResourceLite(*(PERESOURCE *)(a3 + 104));
    }
  }
  else
  {
    if ( (v12 & 1) != 0 )
    {
      v62 = a3;
      if ( *(_WORD *)a3 != 2050 )
        v62 = *(_QWORD *)(a3 + 120);
      ExReleaseResourceLite(*(PERESOURCE *)(v62 + 104));
    }
    if ( (v12 & 8) != 0 )
      RefsReleaseFcb(v8, *(_QWORD *)(a3 + 120));
    v63 = *(_QWORD *)(v8 + 144);
    if ( v63 )
    {
      MsFreeCacheContextResources(*(_QWORD *)(*(_QWORD *)(v8 + 64) + 104LL), v63 + 216);
      MsCleanupFastResourceOwnerEntry(*(_QWORD *)(v8 + 144) + 80LL);
      v64 = *(_DWORD *)(v8 + 8);
      if ( (v64 & 0x10) != 0 )
      {
        RefsFreeNPagedPerProcessorLookaside(RefsIoContextLookasideList, *(_QWORD *)(v8 + 144));
        v64 = *(_DWORD *)(v8 + 8) & 0xFFFFFFEF;
      }
      *(_QWORD *)(v8 + 144) = 0;
      *(_DWORD *)(v8 + 8) = v64 & 0xFFFF7FFF;
    }
  }
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x1c018e078  mov     r11, rsp
0x1c018e07b  mov     [r11+20h], r9
0x1c018e07f  mov     [r11+18h], r8
0x1c018e083  mov     [r11+10h], rdx
0x1c018e087  mov     [r11+8], rcx
0x1c018e08b  push    rbx
0x1c018e08c  push    rsi
0x1c018e08d  push    rdi
0x1c018e08e  push    r12
0x1c018e090  push    r13
0x1c018e092  push    r14
0x1c018e094  push    r15
0x1c018e096  sub     rsp, 150h
0x1c018e09d  mov     r15, r9
0x1c018e0a0  mov     rdi, r8
0x1c018e0a3  mov     r13, rdx
0x1c018e0a6  mov     r14, rcx
0x1c018e0a9  mov     r12, [rsp+188h+arg_20]
0x1c018e0b1  xor     r8d, r8d
0x1c018e0b4  mov     esi, r8d
0x1c018e0b7  mov     [rsp+188h+Status], r8d
0x1c018e0bc  or      qword ptr [r11-88h], 0FFFFFFFFFFFFFFFFh
0x1c018e0c4  mov     [r11-108h], r8
0x1c018e0cb  mov     [r11-0D8h], r8
0x1c018e0d2  mov     [r11-0B8h], r8
0x1c018e0d9  mov     [r11-0C0h], r8
0x1c018e0e0  xorps   xmm0, xmm0
0x1c018e0e3  movups  xmmword ptr [r11-78h], xmm0
0x1c018e0e8  mov     eax, r8d
0x1c018e0eb  mov     [rsp+188h+var_E4], eax
0x1c018e0f2  mov     [r11-68h], r8
0x1c018e0f6  mov     [rsp+188h+var_110], r8b
0x1c018e0fb  mov     [r11-0F8h], r8b
0x1c018e102  mov     [rsp+188h+var_10F], r8b
0x1c018e107  mov     [r11-0F0h], r8
0x1c018e10e  movups  xmmword ptr [r11-58h], xmm0
0x1c018e113  mov     ebx, r8d
0x1c018e116  mov     [rsp+188h+var_118], ebx
0x1c018e11a  cmp     [rdi+10h], r8
0x1c018e11e  jz      loc_1C018E1C9
0x1c018e124  cmp     [r14+38h], r8
0x1c018e128  jnz     loc_1C018E1DE
0x1c018e12e  test    bl, 4
0x1c018e131  jnz     short loc_1C018E1AB
0x1c018e133  mov     rax, [rdi+0F0h]
0x1c018e13a  cmp     [rax+8], r8
0x1c018e13e  jnz     short loc_1C018E1AB
0x1c018e140  mov     eax, [rdi+88h]
0x1c018e146  and     al, 28h
0x1c018e148  cmp     al, 20h ; ' '
0x1c018e14a  jnz     short loc_1C018E1AB
0x1c018e14c  mov     r8b, 1
0x1c018e14f  mov     rdx, rdi
0x1c018e152  call    RefsAcquirePagingResourceShared
0x1c018e157  and     ebx, 0FFFFFFFDh
0x1c018e15a  mov     [rsp+188h+var_118], ebx
0x1c018e15e  mov     rax, [rdi+0F0h]
0x1c018e165  xor     r8d, r8d
0x1c018e168  cmp     [rax+8], r8
0x1c018e16c  jnz     short loc_1C018E17A
0x1c018e16e  mov     eax, [rdi+88h]
0x1c018e174  and     al, 28h
0x1c018e176  cmp     al, 20h ; ' '
0x1c018e178  jz      short loc_1C018E1C4
0x1c018e17a  mov     eax, 802h
0x1c018e17f  cmp     ax, [rdi]
0x1c018e182  mov     rcx, rdi
0x1c018e185  jz      short loc_1C018E18B
0x1c018e187  mov     rcx, [rdi+78h]
0x1c018e18b  mov     rcx, [rcx+68h]; Resource
0x1c018e18f  call    cs:__imp_ExReleaseResourceLite
0x1c018e196  nop     dword ptr [rax+rax+00h]
0x1c018e19b  mov     r8b, 1
0x1c018e19e  mov     rdx, rdi
0x1c018e1a1  call    RefsAcquirePagingResourceExclusive
0x1c018e1a6  or      ebx, 2
0x1c018e1a9  jmp     short loc_1C018E1C0
0x1c018e1ab  mov     r8b, 1
0x1c018e1ae  mov     rdx, rdi
0x1c018e1b1  call    RefsAcquirePagingResourceExclusive
0x1c018e1b6  or      ebx, 2
0x1c018e1b9  mov     [rsp+188h+var_118], ebx
0x1c018e1bd  and     ebx, 0FFFFFFFBh
0x1c018e1c0  mov     [rsp+188h+var_118], ebx
0x1c018e1c4  or      ebx, 1
0x1c018e1c7  jmp     short loc_1C018E1DA
0x1c018e1c9  xor     r8d, r8d
0x1c018e1cc  mov     rdx, rdi
0x1c018e1cf  mov     rcx, r14
0x1c018e1d2  call    RefsAcquireExclusiveScbWithFlags
0x1c018e1d7  or      ebx, 8
0x1c018e1da  mov     [rsp+188h+var_118], ebx
0x1c018e1de  mov     eax, [rdi+130h]
0x1c018e1e4  test    al, 40h
0x1c018e1e6  jz      short loc_1C018E25C
0x1c018e1e8  lea     rax, WPP_GLOBAL_Control
0x1c018e1ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1c018e1f6  cmp     rcx, rax
0x1c018e1f9  jz      short loc_1C018E229
0x1c018e1fb  mov     eax, [rcx+2Ch]
0x1c018e1fe  bt      eax, 8
0x1c018e202  jnb     short loc_1C018E229
0x1c018e204  cmp     byte ptr [rcx+29h], 4
0x1c018e208  jb      short loc_1C018E229
0x1c018e20a  mov     edx, 1Ch
0x1c018e20f  mov     esi, 0C0000123h
0x1c018e214  mov     r9d, esi
0x1c018e217  lea     r8, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids
0x1c018e21e  mov     rcx, [rcx+18h]
0x1c018e222  call    WPP_SF_D
0x1c018e227  jmp     short loc_1C018E22E
0x1c018e229  mov     esi, 0C0000123h
0x1c018e22e  mov     al, cs:RefsStatusDebugEnabled
0x1c018e234  xor     r15d, r15d
0x1c018e237  test    al, al
0x1c018e239  jz      short loc_1C018E24F
0x1c018e23b  mov     r8d, 0E1Ah
0x1c018e241  lea     rdx, aAttrhelpersC; "AttrHelpers.c"
0x1c018e248  mov     ecx, esi; Status
0x1c018e24a  call    RefsStatusDebug
0x1c018e24f  mov     [rsp+188h+Status], esi
0x1c018e253  mov     ebx, [rsp+188h+var_118]
0x1c018e257  jmp     loc_1C018F26E
0x1c018e25c  bt      eax, 10h
0x1c018e260  jnb     short loc_1C018E2BD
0x1c018e262  lea     rax, WPP_GLOBAL_Control
0x1c018e269  mov     rcx, cs:WPP_GLOBAL_Control
0x1c018e270  cmp     rcx, rax
0x1c018e273  jz      short loc_1C018E2A3
0x1c018e275  mov     eax, [rcx+2Ch]
0x1c018e278  bt      eax, 8
0x1c018e27c  jnb     short loc_1C018E2A3
0x1c018e27e  cmp     byte ptr [rcx+29h], 4
0x1c018e282  jb      short loc_1C018E2A3
0x1c018e284  mov     edx, 1Dh
0x1c018e289  mov     esi, 0C000026Eh
0x1c018e28e  mov     r9d, esi
0x1c018e291  lea     r8, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids
0x1c018e298  mov     rcx, [rcx+18h]
0x1c018e29c  call    WPP_SF_D
0x1c018e2a1  jmp     short loc_1C018E2A8
0x1c018e2a3  mov     esi, 0C000026Eh
0x1c018e2a8  mov     al, cs:RefsStatusDebugEnabled
0x1c018e2ae  xor     r15d, r15d
0x1c018e2b1  test    al, al
0x1c018e2b3  jz      short loc_1C018E24F
0x1c018e2b5  mov     r8d, 0E1Fh
0x1c018e2bb  jmp     short loc_1C018E241
0x1c018e2bd  mov     rcx, [rdi+78h]
0x1c018e2c1  call    RefsIsFileOpen
0x1c018e2c6  test    al, al
0x1c018e2c8  jnz     short loc_1C018E33B
0x1c018e2ca  lea     rax, WPP_GLOBAL_Control
0x1c018e2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1c018e2d8  cmp     rcx, rax
0x1c018e2db  jz      short loc_1C018E30B
0x1c018e2dd  mov     eax, [rcx+2Ch]
0x1c018e2e0  bt      eax, 8
0x1c018e2e4  jnb     short loc_1C018E30B
0x1c018e2e6  cmp     byte ptr [rcx+29h], 4
0x1c018e2ea  jb      short loc_1C018E30B
0x1c018e2ec  mov     edx, 1Eh
0x1c018e2f1  mov     esi, 0C0000128h
0x1c018e2f6  mov     r9d, esi
0x1c018e2f9  lea     r8, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids
0x1c018e300  mov     rcx, [rcx+18h]
0x1c018e304  call    WPP_SF_D
0x1c018e309  jmp     short loc_1C018E310
0x1c018e30b  mov     esi, 0C0000128h
0x1c018e310  mov     al, cs:RefsStatusDebugEnabled
0x1c018e316  test    al, al
0x1c018e318  jz      short loc_1C018E32E
0x1c018e31a  mov     r8d, 0E24h
0x1c018e320  lea     rdx, aAttrhelpersC; "AttrHelpers.c"
0x1c018e327  mov     ecx, esi; Status
0x1c018e329  call    RefsStatusDebug
0x1c018e32e  mov     [rsp+188h+Status], esi
0x1c018e332  mov     ebx, [rsp+188h+var_118]
0x1c018e336  jmp     loc_1C018F26B
0x1c018e33b  mov     eax, [rdi+88h]
0x1c018e341  test    al, 20h
0x1c018e343  jnz     short loc_1C018E353
0x1c018e345  xor     r8d, r8d
0x1c018e348  mov     rdx, rdi
0x1c018e34b  mov     rcx, r14
0x1c018e34e  call    RefsUpdateScbFromAttribute
0x1c018e353  mov     rcx, [r15]
0x1c018e356  mov     rdx, [rdi+20h]
0x1c018e35a  cmp     rcx, rdx
0x1c018e35d  jge     loc_1C018E530
0x1c018e363  cmp     rcx, r12
0x1c018e366  jge     loc_1C018E530
0x1c018e36c  test    r13, r13
0x1c018e36f  jz      short loc_1C018E3DC
0x1c018e371  mov     rax, r12
0x1c018e374  sub     rax, rcx
0x1c018e377  mov     [rsp+188h+var_100], rax
0x1c018e37f  mov     r8, rax
0x1c018e382  cmp     r12, rdx
0x1c018e385  jle     short loc_1C018E398
0x1c018e387  mov     rax, rdx
0x1c018e38a  sub     rax, rcx
0x1c018e38d  mov     [rsp+188h+var_100], rax
0x1c018e395  mov     r8, rax
0x1c018e398  mov     ecx, 40000000h
0x1c018e39d  cmp     r8, rcx
0x1c018e3a0  cmovg   rax, rcx
0x1c018e3a4  mov     [rsp+188h+var_100], rax
0x1c018e3ac  mov     [rsp+188h+Priority], eax; int
0x1c018e3b0  mov     [rsp+188h+IoStatus], r15; __int64
0x1c018e3b5  mov     r9, r13
0x1c018e3b8  mov     r8, rdi
0x1c018e3bb  mov     rdx, [r14+48h]; Irp
0x1c018e3bf  mov     rcx, r14; Context
0x1c018e3c2  call    RefsCheckLocksInZeroRange
0x1c018e3c7  mov     esi, eax
0x1c018e3c9  mov     [rsp+188h+Status], eax
0x1c018e3cd  test    eax, eax
0x1c018e3cf  jz      short loc_1C018E3DC
0x1c018e3d1  cmp     eax, 108h
0x1c018e3d6  jnz     loc_1C018F26B
0x1c018e3dc  xor     r9d, r9d
0x1c018e3df  lea     r8d, [r9+1]
0x1c018e3e3  mov     rdx, rdi
0x1c018e3e6  mov     rcx, r14
0x1c018e3e9  call    RefsPostUsnChangeWithOverrideOption
0x1c018e3ee  xor     r11d, r11d
0x1c018e3f1  test    r13, r13
0x1c018e3f4  jz      short loc_1C018E3FC
0x1c018e3f6  bts     dword ptr [r13+50h], 0Ch
0x1c018e3fc  mov     eax, [rdi+88h]
0x1c018e402  test    al, 8
0x1c018e404  jz      loc_1C018E597
0x1c018e40a  mov     r9, [r15]
0x1c018e40d  mov     r15, r12
0x1c018e410  sub     r15, r9
0x1c018e413  mov     [rsp+188h+var_100], r15
0x1c018e41b  mov     rax, [rdi+20h]
0x1c018e41f  cmp     r12, rax
0x1c018e422  jle     short loc_1C018E432
0x1c018e424  mov     r15, rax
0x1c018e427  sub     r15, r9
0x1c018e42a  mov     [rsp+188h+var_100], r15
0x1c018e432  mov     rax, [rdi+0F0h]
0x1c018e439  cmp     [rax+8], r11
0x1c018e43d  jz      loc_1C018E4E8
0x1c018e443  mov     [rsp+188h+var_158], r11b
0x1c018e448  mov     byte ptr [rsp+188h+Priority], 1
0x1c018e44d  mov     [rsp+188h+IoStatus], r15
0x1c018e452  mov     r8, rdi
0x1c018e455  mov     rcx, r14
0x1c018e458  call    RefsCacheCoherencyFlush
0x1c018e45d  mov     esi, eax
0x1c018e45f  mov     [rsp+188h+Status], eax
0x1c018e463  cmp     eax, 0C0000435h
0x1c018e468  jnz     short loc_1C018E4DE
0x1c018e46a  lea     rax, WPP_GLOBAL_Control
0x1c018e471  mov     rcx, cs:WPP_GLOBAL_Control
0x1c018e478  cmp     rcx, rax
0x1c018e47b  jz      short loc_1C018E4AB
0x1c018e47d  test    dword ptr [rcx+2Ch], 100h
0x1c018e484  jz      short loc_1C018E4AB
0x1c018e486  cmp     byte ptr [rcx+29h], 4
0x1c018e48a  jb      short loc_1C018E4AB
0x1c018e48c  mov     edx, 1Fh
0x1c018e491  mov     esi, 0C000001Bh
0x1c018e496  mov     r9d, esi
0x1c018e499  lea     r8, WPP_f59e1edd1d2c3bc65d3d408f7bc0bd6e_Traceguids
0x1c018e4a0  mov     rcx, [rcx+18h]
0x1c018e4a4  call    WPP_SF_D
0x1c018e4a9  jmp     short loc_1C018E4B0
0x1c018e4ab  mov     esi, 0C000001Bh
0x1c018e4b0  mov     al, cs:RefsStatusDebugEnabled
0x1c018e4b6  test    al, al
0x1c018e4b8  jz      short loc_1C018E4CE
0x1c018e4ba  mov     r8d, 0E88h
0x1c018e4c0  lea     rdx, aAttrhelpersC; "AttrHelpers.c"
0x1c018e4c7  mov     ecx, esi; Status
0x1c018e4c9  call    RefsStatusDebug
0x1c018e4ce  mov     [rsp+188h+Status], esi
0x1c018e4d2  mov     r15, [rsp+188h+var_100]
0x1c018e4da  mov     ebx, [rsp+188h+var_118]
0x1c018e4de  xor     eax, eax
0x1c018e4e0  test    esi, esi
0x1c018e4e2  js      loc_1C018F26B
0x1c018e4e8  test    bl, 8
0x1c018e4eb  jnz     short loc_1C018E502
0x1c018e4ed  xor     r8d, r8d
0x1c018e4f0  mov     rdx, rdi
0x1c018e4f3  mov     rcx, r14
0x1c018e4f6  call    RefsAcquireExclusiveScbWithFlags
0x1c018e4fb  or      ebx, 8
0x1c018e4fe  mov     [rsp+188h+var_118], ebx
0x1c018e502  mov     [rsp+188h+Priority], r15d; Size
0x1c018e507  mov     r12, [rsp+188h+arg_18]
0x1c018e50f  mov     eax, [r12]
0x1c018e513  mov     dword ptr [rsp+188h+IoStatus], eax; int
0x1c018e517  mov     r9, rdi; int
0x1c018e51a  xor     edx, edx; int
0x1c018e51c  mov     rcx, r14; int
  ... truncated ...
```
