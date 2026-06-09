# TxfOpenFileProcessing

- ea: `0x14019dc78`
- end: `0x14019f217`
- name: `TxfOpenFileProcessing`
- size: `5535`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, int, int, __int64, __int64, __int64 *)`
- caller_count: `7`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14019c120`
- `0x14019ca80`
- `0x140219550`
- `0x140227518`
- `0x1402376ac`
- `0x140261f40`
- `0x14029cab0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14001c8c0`
- `0x14002b520`
- `0x14002b680`
- `0x140034560`
- `0x140035e70`
- `0x1400593c0`
- `0x1400596c0`
- `0x1400b454c`
- `0x14012be00`
- `0x14012c1ec`
- `0x14013c2d0`
- `0x140140380`
- `0x14017e930`
- `0x140187da0`
- `0x14018a850`
- `0x14018dc4c`
- `0x14018e07c`
- `0x140192470`
- `0x140196850`
- `0x140196ad0`
- `0x14019dc78`
- `0x1401ac080`
- `0x1401c2910`
- `0x140204dac`
- `0x140243c00`
- `0x140245de0`
- `0x140264c54`
- `0x1402654c8`
- `0x14029ac70`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14019ea8c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14019ea8c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14019ea62`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14019ea62`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14019e854`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14019e854`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f135`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f15a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f135`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f15a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e077`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e1f8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e221`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e077`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e1f8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e221`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14019e937`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14019e937`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019eada`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019eada`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019ea32`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019ea32`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14019e917`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14019e917`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019dee1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e17a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e6ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019ee02`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f013`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f0f6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019dee1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e17a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e6ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019ee02`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f013`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f0f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019ddc5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e14b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e532`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e555`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e5f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e652`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019ef5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019efef`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f185`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f1de`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acb94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019ddc5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e14b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e532`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e555`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e5f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e652`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019ef5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019efef`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f185`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f1de`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acb94`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14019e1cc`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14019e1cc`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019dde0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019de65`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019ed0d`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019efca`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019dde0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019de65`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019ed0d`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019efca`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e504`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e5b9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e504`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e5b9`
- `ntoskrnl!ExRaiseStatus` at `0x14019dfe2`
- `ntoskrnl!ExRaiseStatus` at `0x14019e02b`
- `ntoskrnl!ExRaiseStatus` at `0x14019e405`
- `ntoskrnl!ExRaiseStatus` at `0x14019e89d`
- `ntoskrnl!ExRaiseStatus` at `0x14019dfe2`
- `ntoskrnl!ExRaiseStatus` at `0x14019e02b`
- `ntoskrnl!ExRaiseStatus` at `0x14019e405`
- `ntoskrnl!ExRaiseStatus` at `0x14019e89d`

## pseudocode

```c
__int64 __fastcall TxfOpenFileProcessing(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 *a9)
{
  __int64 v9; // rdi
  unsigned __int8 v12; // r12
  int v13; // ecx
  char v14; // r10
  __int64 v15; // r14
  __int64 v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r15
  _BYTE *v20; // rdx
  unsigned int v21; // r15d
  __int64 v22; // r15
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  char v26; // al
  _QWORD *v27; // r15
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r15
  _QWORD *v31; // rax
  PVOID v32; // rax
  int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // r12
  _QWORD *v36; // r15
  int v37; // r15d
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  char v41; // al
  __int64 v42; // r15
  _QWORD *NextChildScb; // rax
  __int16 v44; // r10
  char v45; // r11
  int v46; // eax
  _DWORD *v47; // rax
  _DWORD *v48; // r15
  int v49; // edx
  __int64 v50; // rax
  _QWORD *v51; // r15
  __int64 v52; // rcx
  int v53; // edx
  unsigned int v54; // ecx
  USHORT v55; // r8
  unsigned int v56; // eax
  __int64 v57; // rcx
  volatile signed __int32 *v58; // rax
  volatile signed __int32 *v59; // r15
  _DWORD *v60; // rax
  __int64 v61; // rax
  __int64 v62; // r11
  __int64 v63; // rdx
  __int64 v64; // r10
  __int64 v65; // r8
  __int64 TxfFo; // rax
  _DWORD *v67; // rdx
  __int64 v68; // rax
  int v70; // [rsp+20h] [rbp-D8h]
  unsigned __int8 v71; // [rsp+50h] [rbp-A8h]
  NTSTATUS v72; // [rsp+54h] [rbp-A4h]
  NTSTATUS v73; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v74; // [rsp+60h] [rbp-98h]
  signed __int32 v75; // [rsp+68h] [rbp-90h] BYREF
  __int64 v76; // [rsp+70h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-80h] BYREF
  _DWORD *v78; // [rsp+88h] [rbp-70h]
  __int64 v79; // [rsp+90h] [rbp-68h]
  PVOID Entry; // [rsp+98h] [rbp-60h]
  __int64 v81; // [rsp+A0h] [rbp-58h]
  __int64 v82; // [rsp+A8h] [rbp-50h]
  char v83; // [rsp+100h] [rbp+8h] BYREF
  __int64 v84; // [rsp+108h] [rbp+10h] BYREF
  _QWORD *v85; // [rsp+118h] [rbp+20h]

  v85 = a4;
  v84 = a2;
  v9 = a3;
  v12 = 0;
  v83 = 0;
  v13 = *(_DWORD *)(a1 + 436);
  v14 = (a5 & 0x10D0116) != 0 || (v13 & 6) != 0;
  v71 = v14;
  v15 = 0;
  v81 = 0;
  v16 = *(_QWORD *)(a2 + 320);
  v72 = 0;
  v75 = 0;
  v76 = 0;
  Entry = 0;
  LODWORD(v78) = *(_DWORD *)(a1 + 28);
  if ( a8 )
    v17 = *(_QWORD *)(a8 + 176);
  else
    v17 = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 184LL);
  v79 = v17;
  v18 = *(_DWORD *)(v16 + 136);
  if ( (v18 & 0x4000) != 0 && (v13 & 0x100000) == 0 && ((v18 & 0x80000) == 0 || (*(_DWORD *)(a2 + 4) & 0x40000) != 0) )
    TxfParkRequest(a1, *(_QWORD *)(v16 + 24) + 1280LL, 0);
  if ( a8 )
  {
    v24 = *(_QWORD *)(a1 + 400);
    if ( !v24 || v14 && !*(_QWORD *)(v24 + 240) )
    {
      TxfSetupTransactionContextForCreate(a1, a8, v14, a2);
      v14 = v71;
    }
  }
  v19 = *(_QWORD *)(a1 + 400);
  v74 = v19;
  if ( !v19 )
    goto LABEL_6;
  a3 = a2 + 8;
  v33 = *(_DWORD *)(a2 + 8);
  if ( v33 != 5 && *(_DWORD *)(*(_QWORD *)(a2 + 320) + 88LL) != v33
    || v16 == *(_QWORD *)(*(_QWORD *)(v16 + 16) + 6248LL)
    || !v14
    || a6 )
  {
    if ( v9 )
    {
      if ( !*(_QWORD *)(v9 + 528) )
        TxfSetUpNtfsPtrs(v9, 0, 0);
    }
    else if ( !*(_QWORD *)(a2 + 328) )
    {
      *(_QWORD *)(a2 + 328) = TxfCreateTxfFcb(*(_QWORD *)(a2 + 96), v16, (_QWORD *)a3, *(_WORD *)(a2 + 4) & 0x400, 0, 0);
    }
    v15 = *(_QWORD *)(a2 + 328);
    v81 = v15;
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v15 + 136), 1u);
    v83 = 1;
    v12 = 0;
    if ( a6 && v19 != *(_QWORD *)(v15 + 24) )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v15 + 136));
      v83 = 0;
      goto LABEL_6;
    }
    ExReleaseResourceLite(*(PERESOURCE *)(v15 + 136));
    v83 = 0;
    v21 = NtfsUpgradeFileSecurity(a1);
    v72 = v21;
    v73 = v21;
    if ( v21 )
      goto LABEL_262;
    if ( (_DWORD)v78 != *(_DWORD *)(a1 + 28) )
      NtfsCheckpointCurrentTransaction(a1);
    v15 = *(_QWORD *)(a2 + 328);
    v81 = v15;
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v15 + 136), 1u);
    v83 = 1;
    if ( (v71 || (v34 = *(_QWORD *)(v15 + 24)) != 0 && v34 == v74) && (*(_DWORD *)(a1 + 436) & 2) == 0 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v15 + 136));
      v83 = 0;
      v35 = a8;
      v36 = v85;
      TxfPrepareFileForTxfLogging(a1, *(void **)(a1 + 400), a2, v85, a8, 1, 0, (_DWORD)v78 != 0);
    }
    else
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v15 + 136));
      v83 = 0;
      v36 = v85;
      v35 = a8;
    }
    if ( v35
      && v71
      && a9
      && (*(_DWORD *)(v79 + 16) & 0x1000) != 0
      && v36
      && v9
      && (!*(_WORD *)(v9 + 264) || *(_DWORD *)(v9 + 256) != 128) )
    {
      v37 = TxfPrepareFileForPotentialTxLinkDelete(a1);
      v72 = v37;
      v73 = v37;
      if ( v37 < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)v37 < 0xFFFFFFED
          && v37 != -1073741802
          && v37 != -1073741807
          && (unsigned int)(v37 + 2147483643) > 1
          && v37 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v37, 0x280BDCu);
        }
        ExRaiseStatus(v37);
      }
      *(_DWORD *)(v35 + 192) |= 1u;
    }
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v15 + 136), 1u);
    v12 = 1;
    v83 = 1;
    if ( v71 )
    {
      if ( *(_DWORD *)(a2 + 284) )
      {
        if ( a2 != *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 96) + 32LL) + 184LL) )
        {
          v38 = *(_QWORD *)(*(_QWORD *)(v15 + 40) + 96LL);
          if ( !v38 || a2 != *(_QWORD *)(v38 + 184) )
            NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2624515);
        }
      }
      v39 = *(_DWORD *)(v15 + 4);
      if ( (v39 & 1) != 0 )
      {
        if ( (a5 & 6) != 0 )
          *(_DWORD *)(v15 + 4) = v39 | 0x4000000;
        if ( (*(_DWORD *)(a2 + 4) & 0x1800000) != 0 )
        {
          v57 = v74;
          _InterlockedOr((volatile signed __int32 *)(v74 + 16), 4u);
          goto LABEL_178;
        }
      }
      else
      {
        if ( !*(_BYTE *)v79 && (v9 && *(_DWORD *)(v9 + 256) == 128 || (*(_DWORD *)(a2 + 176) & 0x10000000) == 0) )
        {
          v40 = *(_QWORD *)(*(_QWORD *)(v79 + 8) + 8LL);
          if ( (*(_DWORD *)(v40 + 24) & 0x2000000) != 0 )
          {
            *(_DWORD *)(v40 + 20) &= ~0x20u;
            v41 = a5 & 0xDF;
            a5 &= ~0x20u;
          }
          else
          {
            v41 = a5;
          }
          if ( (v41 & 0x20) != 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0190044, 0x280C23u);
            v73 = -1072103356;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0190044, 0x280C23u);
            ExRaiseStatus(-1072103356);
          }
        }
        v42 = 0;
        while ( 1 )
        {
          NextChildScb = NtfsGetNextChildScb(a2, v42, 0);
          v42 = (__int64)NextChildScb;
          if ( !NextChildScb )
            break;
          v46 = *((_DWORD *)NextChildScb + 64);
          if ( (v46 == 128 && *(_WORD *)v42 == 1797
             || v46 == 160
             && *(_WORD *)(v42 + 264) == v44
             && **(_QWORD **)(v42 + 272) == 0x30003300490024LL
             && (unsigned __int16)(*(_WORD *)v42 - 1795) <= 1u)
            && FsRtlCurrentOplock((POPLOCK)(v42 + 88)) )
          {
            v47 = TxfSearchAddTxfFcbCleanupList(*(_QWORD *)(a1 + 144), 0, 5, 0, 1);
            v47[4] |= 0x80000u;
            *((_QWORD *)v47 + 5) = *(_QWORD *)(a2 + 8);
            *((_BYTE *)v47 + 48) = 0;
            ExRaiseStatus(-1073741608);
          }
        }
        v48 = TxfSearchAddTxfFcbCleanupList(a1, v15, 1, 0, v45);
        v48[4] |= 0x800u;
        *(_DWORD *)(v15 + 4) |= 1u;
        v49 = *(_DWORD *)(v15 + 4);
        v50 = v74;
        *(_QWORD *)(v15 + 24) = v74;
        if ( (*(_DWORD *)(a2 + 4) & 0x1800000) != 0 )
        {
          _InterlockedOr((volatile signed __int32 *)(v50 + 16), 4u);
          v49 = *(_DWORD *)(v15 + 4);
        }
        if ( (a5 & 6) != 0 )
          *(_DWORD *)(v15 + 4) = v49 | 0x4000000;
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v15 + 40) + 16LL) + 6176LL));
        ++*(_WORD *)(v15 + 16);
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v15 + 40) + 16LL) + 6176LL));
        TxfTransAddTxfFcbToPendingList(v74, v15);
        if ( *(_QWORD *)(a2 + 296) )
          NtfsFreeFcbUsnRecord(a1, &v84);
        *(_DWORD *)(v15 + 4) &= ~0x10000u;
        if ( (*(_DWORD *)(a1 + 436) & 2) == 0 )
        {
          v48[4] &= ~0x800u;
          *(_DWORD *)(*(_QWORD *)(a2 + 328) + 148LL) |= 0x400000u;
          if ( a7 )
          {
            v51 = v85;
            if ( v85 )
            {
              v52 = v85[3];
              if ( v52 )
              {
                a3 = v85[24];
                if ( (*(_BYTE *)(a3 + 65) & 3) != 2 )
                {
                  *(_QWORD *)&DestinationString.Length = 0;
                  DestinationString.Buffer = 0;
                  v53 = *(unsigned __int16 *)(v52 + 656);
                  v54 = v53 + 2 * *(unsigned __int8 *)(a3 + 64);
                  v55 = v54 + 2;
                  if ( (unsigned __int16)v53 <= 2u )
                    v55 = v54;
                  v56 = v54 + 2;
                  if ( (unsigned __int16)v53 <= 2u )
                    v56 = v54;
                  if ( v56 > 0xFFFE )
                  {
                    if ( NtfsStatusDebugFlags )
                      NtfsStatusTraceAndDebugInternal(a1, 0xC0000106, 0x280CCDu);
                    NtfsRaiseStatusInternal(a1, -1073741562, 0, 0, 2624717);
                  }
                  DestinationString.MaximumLength = v55;
                  DestinationString.Buffer = (PWSTR)ExAllocatePoolWithTag(PoolType, v56, 0x30667854u);
                  if ( DestinationString.Buffer )
                  {
                    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v51[3] + 656LL));
                    if ( *(_WORD *)(v51[3] + 656LL) > 2u )
                      RtlAppendUnicodeToString(&DestinationString, L"\\");
                    memmove(
                      (char *)DestinationString.Buffer + DestinationString.Length,
                      (const void *)(v51[24] + 66LL),
                      2LL * *(unsigned __int8 *)(v51[24] + 64LL));
                    DestinationString.Length += 2 * *(unsigned __int8 *)(v51[24] + 64LL);
                    ExFreePoolWithTag(DestinationString.Buffer, 0);
                  }
                }
              }
            }
          }
        }
      }
    }
    v57 = v74;
LABEL_178:
    if ( (*(_DWORD *)(v15 + 4) & 1) != 0 && *(_QWORD *)(v15 + 24) == v57 && (*(_DWORD *)(a1 + 436) & 2) == 0 )
    {
      v21 = TxfSavepointProcessing(a1, v57, a2, 0, 0, 0, 1, 1, 1);
      v72 = v21;
      v73 = v21;
      if ( v21 )
        goto LABEL_262;
      if ( (*(_DWORD *)(v15 + 4) & 0x8000) == 0 )
        TxfLogFcbInfoRecord(a1, v74, a2, 1, 0, 0);
    }
    if ( (*(_DWORD *)(v15 + 4) & 8) == 0 )
    {
      v27 = ExAllocateFromLookasideListEx(&TxfFcbInfoLookasideList);
      memset(v27, 0, 0x50u);
      *((_OWORD *)v27 + 1) = *(_OWORD *)(a2 + 128);
      *((_OWORD *)v27 + 2) = *(_OWORD *)(a2 + 144);
      *((_OWORD *)v27 + 3) = *(_OWORD *)(a2 + 160);
      v27[8] = *(_QWORD *)(a2 + 176);
      *((_DWORD *)v27 + 18) = *(_DWORD *)(a2 + 280);
      v28 = (_QWORD *)(v15 + 88);
      v29 = *(_QWORD *)(v15 + 88);
      if ( *(_QWORD *)(v29 + 8) != v15 + 88 )
        __fastfail(3u);
      *v27 = v29;
      v27[1] = v28;
      *(_QWORD *)(v29 + 8) = v27;
      *v28 = v27;
      *(_DWORD *)(v15 + 4) |= 8u;
      *((_WORD *)v27 + 39) |= 1u;
    }
    if ( v9 )
    {
      v84 = *(_QWORD *)(v9 + 528);
      v58 = (volatile signed __int32 *)TxfCurrentWritableVersion(v84, 1, 1);
      v59 = v58;
      if ( v58 )
      {
        v75 = *((_DWORD *)v58 + 2);
        Entry = (PVOID)v58;
      }
      if ( (*(_DWORD *)(a1 + 436) & 4) == 0
        && *(_DWORD *)(v9 + 256) == 128
        && (((*(_BYTE *)(v84 + 24) & 1) == 0) & !_bittest(&v75, 0xFu)) != 0 )
      {
        TxfFlushStreamForOpenProcessing(a1, v9, &v75, &v83, &v76);
        *(_DWORD *)(*(_QWORD *)(v9 + 528) + 24LL) |= 0x80000000;
        v12 = v83;
      }
      if ( !v59 )
      {
        TxfCreateTxfVscb(a1, v9, 1, 0);
        v59 = (volatile signed __int32 *)TxfCurrentWritableVersion(v84, 1, 1);
        Entry = (PVOID)v59;
      }
      *((_DWORD *)v59 + 2) |= v75;
      if ( (*(_DWORD *)(v15 + 4) & 1) != 0 && *(_QWORD *)(v15 + 24) == v74 )
      {
        if ( (v59[2] & 2) != 0 )
        {
          v21 = TxfSavepointProcessing(a1, v74, a2, v9, (__int64)v85, 0, v12, 1, 1);
          v72 = v21;
          v73 = v21;
          if ( v21 )
            goto LABEL_262;
          if ( *(_DWORD *)(a1 + 28) != (_DWORD)v78 )
            NtfsCheckpointCurrentTransaction(a1);
        }
        else
        {
          v60 = TxfSearchAddTxfFcbCleanupList(a1, v15, 1, 0, 0);
          v78 = v60;
          _InterlockedAdd(v59 + 1, 1u);
          _InterlockedOr(v59 + 2, 2u);
          *((_QWORD *)v60 + 3) = v59;
          v60[4] |= 0x400u;
          v61 = v84;
          *(_DWORD *)(v84 + 24) |= 0x20u;
          if ( (*(_DWORD *)(a1 + 436) & 4) == 0 && *(_DWORD *)(v9 + 256) == 128 && (*(_DWORD *)(v61 + 24) & 1) == 0 )
          {
            if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v9 + 184) + 112LL)) )
            {
              *(_DWORD *)(a1 + 436) |= 0x10000u;
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2625074);
            }
            if ( *(_QWORD *)(v74 + 320) != v74 + 320 )
              _InterlockedOr(v59 + 2, 0x100u);
            v30 = v84;
            if ( (*(_DWORD *)(v84 + 24) & 8) == 0 )
              TxfLogCurrentAttrSizesUndo(a1, v74, v9, 1);
            ExReleaseResourceLite(*(PERESOURCE *)(v15 + 136));
            v83 = 0;
            NtfsDeleteInternalAttributeStream(a1, v9, 1, 0);
            ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v15 + 136), 1u);
            v12 = 1;
            v83 = 1;
            _InterlockedAdd((volatile signed __int32 *)(v9 + 212), 1u);
            v76 = v9;
            if ( !*(_QWORD *)(v30 + 112)
              && (*(_DWORD *)(v9 + 208) && (unsigned int)(*(_DWORD *)(v9 + 212) - 1) > *(_DWORD *)(v30 + 32)
               || !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v9 + 288) + 16LL), 0))
              && *(_DWORD *)(*(_QWORD *)(v9 + 288) + 64LL) )
            {
              v31 = ExAllocateFromLookasideListEx(&TxfDefaultReaderSectionLookasideList);
              *(_QWORD *)(v30 + 112) = v31;
              *v31 = *(_QWORD *)(v9 + 288);
              *(_QWORD *)(*(_QWORD *)(v30 + 112) + 8LL) = v9;
              v32 = ExAllocateFromLookasideListEx(&NtfsScbNonpagedLookasideList);
              *(_QWORD *)(v9 + 288) = v32;
              memset(v32, 0, 0x48u);
              **(_WORD **)(v9 + 288) = 1799;
              *(_WORD *)(*(_QWORD *)(v9 + 288) + 2LL) = 72;
              *(_QWORD *)(*(_QWORD *)(v9 + 288) + 40LL) = *(_QWORD *)(v9 + 192);
              *(_DWORD *)(*(_QWORD *)(v9 + 288) + 68LL) = 0;
            }
            NtfsCheckpointCurrentTransaction(a1);
            _InterlockedDecrement((volatile signed __int32 *)(v9 + 212));
            v76 = 0;
            v78[4] &= ~0x400u;
          }
        }
      }
    }
    if ( !a9 )
    {
      v19 = v74;
LABEL_6:
      v15 = *(_QWORD *)(a2 + 328);
      v81 = v15;
      if ( !v12 && v15 )
      {
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v15 + 136), 1u);
        v12 = 1;
        v83 = 1;
      }
      v20 = (_BYTE *)v79;
      if ( !*(_BYTE *)v79 )
      {
        if ( v15
          && (*(_DWORD *)(v15 + 4) & 0x4200000) != 0
          && (v9 && *(_DWORD *)(v9 + 256) == 128 || (*(_DWORD *)(a2 + 176) & 0x10000000) == 0)
          && (v19 == *(_QWORD *)(v15 + 24) || !v19) )
        {
          v25 = *(_QWORD *)(*(_QWORD *)(v79 + 8) + 8LL);
          if ( (*(_DWORD *)(v25 + 24) & 0x2000000) != 0 )
          {
            *(_DWORD *)(v25 + 20) &= ~0x20u;
            v26 = a5 & 0xDF;
            a5 &= ~0x20u;
          }
          else
          {
            v26 = a5;
          }
          if ( (v26 & 0x20) != 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0190044, 0x280FD8u);
            v73 = -1072103356;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0190044, 0x280FD8u);
            ExRaiseStatus(-1072103356);
          }
        }
        if ( !*v20 )
        {
          if ( v9 )
          {
            v23 = *(_QWORD *)(v9 + 528);
            if ( v23 )
            {
              if ( (*(_DWORD *)(v23 + 24) & 0x1000) != 0 )
              {
                v12 = 0;
                if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a2 + 112)) )
                {
                  *(_DWORD *)(a1 + 4) |= 0x10000u;
                  NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2625513);
                }
                if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v9 + 528) + 64LL) + 136LL)) )
                {
                  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v9 + 184) + 328LL) + 136LL));
                  ExAcquireResourceExclusiveLite(
                    *(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v9 + 184) + 328LL) + 136LL),
                    1u);
                }
                v83 = 0;
                TxfPublishCommittedChangesToDefaultReaderSection(a1, v9);
              }
            }
          }
        }
      }
      if ( !v19 )
      {
        if ( v9 )
        {
          v22 = *(_QWORD *)(v9 + 528);
          if ( v22 )
          {
            if ( v71 && !a6 && (*(_DWORD *)(a1 + 436) & 0x80008) == 0 )
            {
              if ( *(_QWORD *)(v22 + 112) )
              {
                if ( v12 )
                {
                  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v22 + 64) + 136LL));
                  v12 = 0;
                  v83 = 0;
                }
                if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a2 + 112)) )
                {
                  *(_DWORD *)(a1 + 436) |= 0x10000u;
                  NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2625566);
                }
                if ( *(_QWORD *)(*(_QWORD *)(v9 + 288) + 16LL) )
                {
                  _InterlockedAdd((volatile signed __int32 *)(v9 + 212), 1u);
                  v76 = v9;
                  LOBYTE(v70) = 0;
                  v73 = NtfsFlushUserStream(a1, v9, 0, 0, v70);
                  NtfsNormalizeAndCleanupTransaction(a1, &v73);
                  if ( (*(_DWORD *)(v9 + 200) & 0x200) != 0 )
                    NtfsWriteFileSizes(a1, v9, 0, 1, 1, 1);
                  NtfsPurgeCacheSection(a1, (__int64 *)v9, 0, 0, 0);
                  _InterlockedDecrement((volatile signed __int32 *)(v9 + 212));
                  v76 = 0;
                  v72 = v73;
                }
                NtfsDeleteInternalAttributeStream(a1, v9, 1, 0);
              }
              if ( !v12 )
              {
                ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v22 + 64) + 136LL), 1u);
                v83 = 1;
              }
              if ( *(_QWORD *)(v22 + 112) )
              {
                v67 = *(_DWORD **)(v9 + 288);
                if ( !v67[16] )
                {
                  if ( (v67[17] & 1) != 0 )
                    *(_WORD *)v67 = 0;
                  else
                    ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, v67);
                }
                *(_QWORD *)(v9 + 288) = **(_QWORD **)(v22 + 112);
                ExFreeToLookasideListEx(&TxfDefaultReaderSectionLookasideList, *(PVOID *)(v22 + 112));
                *(_QWORD *)(v22 + 112) = 0;
              }
              v68 = *(_QWORD *)(v22 + 56);
              if ( v68 )
                _InterlockedOr((volatile signed __int32 *)(v68 + 8), 1u);
              ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v22 + 64) + 136LL));
              v12 = 0;
              v83 = 0;
            }
          }
        }
      }
      v21 = v72;
      goto LABEL_262;
    }
    v82 = 0;
    if ( !v12 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v15 + 136), 1u);
      v83 = 1;
    }
    v62 = a8;
    v63 = *(unsigned __int16 *)(a8 + 70);
    if ( v71 )
    {
      if ( (unsigned __int16)v63 <= 0xFFFDu )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC0190025, 0x280F1Fu);
        NtfsRaiseStatusInternal(a1, -1072103387, 0, 0, 2625311);
      }
      *(_WORD *)(a8 + 70) = -1;
      v63 = 0xFFFF;
    }
    else if ( (_WORD)v63 == 0xFFFE )
    {
      v19 = v74;
      if ( v74 == *(_QWORD *)(v15 + 24) )
      {
        *(_WORD *)(a8 + 70) = -1;
        v63 = 0xFFFF;
      }
      else
      {
        *(_WORD *)(a8 + 70) = 0;
        v63 = 0;
      }
      goto LABEL_220;
    }
    v19 = v74;
LABEL_220:
    v64 = *(_QWORD *)(v9 + 528);
    v65 = *(_QWORD *)(v64 + 56);
    v82 = v65;
    if ( (_WORD)v63 == 0xFFFF )
    {
      v63 = 0xFFFF;
    }
    else
    {
      while ( 1 )
      {
        if ( !v65 )
          goto LABEL_81;
        if ( *(_WORD *)(v65 + 304) <= (unsigned __int16)v63 || (*(_DWORD *)(v65 + 8) & 1) != 0 )
          break;
        v65 = *(_QWORD *)(v65 + 32);
        v82 = v65;
      }
      if ( *(_WORD *)(v65 + 304) != (_WORD)v63 )
      {
LABEL_81:
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC0190022, 0x280F5Du);
        NtfsRaiseStatusInternal(a1, -1072103390, 0, 0, 2625373);
      }
      if ( (_WORD)v63 )
      {
        if ( (*(_DWORD *)(v65 + 8) & 0x2000) != 0 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC0190023, 0x280F70u);
          NtfsRaiseStatusInternal(a1, -1072103389, 0, 0, 2625392);
        }
      }
      else
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v65 + 16) + 24LL) & 1) != 0 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC0190022, 0x280F67u);
          NtfsRaiseStatusInternal(a1, -1072103390, 0, 0, 2625383);
        }
        v63 = 0;
      }
    }
    if ( (_WORD)v63 && *(_QWORD *)(*(_QWORD *)(v64 + 64) + 24LL) != *(_QWORD *)(a1 + 400) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC0190024, 0x280F7Bu);
      NtfsRaiseStatusInternal(a1, -1072103388, 0, 0, 2625403);
    }
    if ( !v62 )
      v63 = 0xFFFF;
    TxfFo = TxfCreateTxfFo(a1, v63, v65, v71);
    *a9 = TxfFo;
    ExReleaseResourceLite(*(PERESOURCE *)(v15 + 136));
    v12 = 0;
    v83 = 0;
    if ( v71 && a7 )
      *(_DWORD *)(a7 + 80) &= ~0x10u;
    goto LABEL_6;
  }
  v21 = -1072103361;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC019003F, 0x280B14u);
  v73 = -1072103361;
LABEL_262:
  if ( v76 )
    _InterlockedDecrement((volatile signed __int32 *)(v76 + 212));
  if ( Entry )
  {
    TxfDereferenceTxfVscb((volatile signed __int32 *)Entry, 0, a3, v12);
    v12 = 0;
  }
  if ( v12 )
    ExReleaseResourceLite(*(PERESOURCE *)(v15 + 136));
  return v21;
}

```

## disassembly

```asm
0x14019dc78  mov     r11, rsp
0x14019dc7b  mov     [r11+20h], r9
0x14019dc7f  mov     [r11+10h], rdx
0x14019dc83  push    rbx
0x14019dc84  push    rsi
0x14019dc85  push    rdi
0x14019dc86  push    r12
0x14019dc88  push    r13
0x14019dc8a  push    r14
0x14019dc8c  push    r15
0x14019dc8e  sub     rsp, 0C0h
0x14019dc95  mov     rdi, r8
0x14019dc98  mov     r13, rdx
0x14019dc9b  mov     rbx, rcx
0x14019dc9e  xor     r9d, r9d
0x14019dca1  mov     r12b, r9b
0x14019dca4  mov     [r11+8], r9b
0x14019dca8  mov     ecx, [rcx+1B4h]
0x14019dcae  test    cl, 6
0x14019dcb1  setnz   r10b
0x14019dcb5  test    dword ptr [r11+28h], 10D0116h
0x14019dcbd  setnz   al
0x14019dcc0  or      r10b, al
0x14019dcc3  mov     [rsp+0F8h+var_A8], r10b
0x14019dcc8  mov     r14d, r9d
0x14019dccb  mov     [r11-58h], r9
0x14019dccf  mov     rsi, [rdx+140h]
0x14019dcd6  mov     [rsp+0F8h+var_A4], r9d
0x14019dcdb  mov     [rsp+0F8h+var_90], r9d
0x14019dce0  mov     [rsp+0F8h+var_88], r9
0x14019dce5  mov     [r11-60h], r9
0x14019dce9  mov     eax, [rbx+1Ch]
0x14019dcec  mov     dword ptr [rsp+0F8h+var_70], eax
0x14019dcf3  mov     rdx, [rsp+0F8h+arg_38]
0x14019dcfb  test    rdx, rdx
0x14019dcfe  jz      loc_14019F1EC
0x14019dd04  mov     rax, [rdx+0B0h]
0x14019dd0b  mov     [rsp+0F8h+var_68], rax
0x14019dd13  mov     eax, [rsi+88h]
0x14019dd19  bt      eax, 0Eh
0x14019dd1d  jb      loc_14019E411
0x14019dd23  test    rdx, rdx
0x14019dd26  jnz     loc_14019DEA3
0x14019dd2c  mov     r15, [rbx+190h]
0x14019dd33  mov     [rsp+0F8h+var_98], r15
0x14019dd38  test    r15, r15
0x14019dd3b  jnz     loc_14019E460
0x14019dd41  lea     esi, [r15+1]
0x14019dd45  mov     r14, [r13+148h]
0x14019dd4c  mov     [rsp+0F8h+var_58], r14
0x14019dd54  test    r12b, r12b
0x14019dd57  jz      loc_14019DECE
0x14019dd5d  mov     rdx, [rsp+0F8h+var_68]
0x14019dd65  cmp     [rdx], r9b
0x14019dd68  jz      loc_14019DE29
0x14019dd6e  test    r15, r15
0x14019dd71  jz      short loc_14019DD7D
0x14019dd73  mov     r15d, [rsp+0F8h+var_A4]
0x14019dd78  jmp     loc_14019F1A4
0x14019dd7d  test    rdi, rdi
0x14019dd80  jz      short loc_14019DD73
0x14019dd82  mov     r15, [rdi+210h]
0x14019dd89  test    r15, r15
0x14019dd8c  jz      short loc_14019DD73
0x14019dd8e  cmp     [rsp+0F8h+var_A8], r9b
0x14019dd93  jz      short loc_14019DD73
0x14019dd95  cmp     [rsp+0F8h+arg_28], r9d
0x14019dd9d  jnz     short loc_14019DD73
0x14019dd9f  test    dword ptr [rbx+1B4h], 80008h
0x14019dda9  jnz     short loc_14019DD73
0x14019ddab  cmp     [r15+70h], r9
0x14019ddaf  jz      loc_14019F0E3
0x14019ddb5  test    r12b, r12b
0x14019ddb8  jz      short loc_14019DDDC
0x14019ddba  mov     rcx, [r15+40h]
0x14019ddbe  mov     rcx, [rcx+88h]; Resource
0x14019ddc5  call    cs:__imp_ExReleaseResourceLite
0x14019ddcc  nop     dword ptr [rax+rax+00h]
0x14019ddd1  xor     r12b, r12b
0x14019ddd4  mov     [rsp+0F8h+arg_0], r12b
0x14019dddc  mov     rcx, [r13+70h]; Resource
0x14019dde0  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14019dde7  nop     dword ptr [rax+rax+00h]
0x14019ddec  xor     r13d, r13d
0x14019ddef  test    al, al
0x14019ddf1  jnz     loc_14019F03A
0x14019ddf7  mov     eax, [rbx+1B4h]
0x14019ddfd  bts     eax, 10h
0x14019de01  mov     [rbx+1B4h], eax
0x14019de07  mov     al, cs:NtfsStatusDebugFlags
0x14019de0d  mov     [rsp+0F8h+var_D8], 28101Eh
0x14019de16  xor     r9d, r9d
0x14019de19  xor     r8d, r8d
0x14019de1c  mov     edx, 0C00000D8h
0x14019de21  mov     rcx, rbx
0x14019de24  call    NtfsRaiseStatusInternal
0x14019de29  test    r14, r14
0x14019de2c  jnz     loc_14019DF00
0x14019de32  cmp     [rdx], r9b
0x14019de35  jnz     loc_14019DD6E
0x14019de3b  test    rdi, rdi
0x14019de3e  jz      loc_14019DD6E
0x14019de44  mov     rax, [rdi+210h]
0x14019de4b  test    rax, rax
0x14019de4e  jz      loc_14019DD6E
0x14019de54  test    dword ptr [rax+18h], 1000h
0x14019de5b  jz      loc_14019DD6E
0x14019de61  mov     rcx, [r13+70h]; Resource
0x14019de65  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14019de6c  nop     dword ptr [rax+rax+00h]
0x14019de71  xor     r12d, r12d
0x14019de74  test    al, al
0x14019de76  jnz     loc_14019EFB8
0x14019de7c  bts     dword ptr [rbx+4], 10h
0x14019de81  mov     al, cs:NtfsStatusDebugFlags
0x14019de87  mov     [rsp+0F8h+var_D8], 280FE9h
0x14019de90  xor     r9d, r9d
0x14019de93  xor     r8d, r8d
0x14019de96  mov     edx, 0C00000D8h
0x14019de9b  mov     rcx, rbx
0x14019de9e  call    NtfsRaiseStatusInternal
0x14019dea3  mov     rax, [rbx+190h]
0x14019deaa  test    rax, rax
0x14019dead  jnz     loc_14019E445
0x14019deb3  mov     r9, r13
0x14019deb6  mov     r8b, r10b
0x14019deb9  mov     rcx, rbx
0x14019debc  call    TxfSetupTransactionContextForCreate
0x14019dec1  mov     r10b, [rsp+0F8h+var_A8]
0x14019dec6  xor     r9d, r9d
0x14019dec9  jmp     loc_14019DD2C
0x14019dece  test    r14, r14
0x14019ded1  jz      loc_14019DD5D
0x14019ded7  mov     dl, sil; Wait
0x14019deda  mov     rcx, [r14+88h]; Resource
0x14019dee1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14019dee8  nop     dword ptr [rax+rax+00h]
0x14019deed  mov     r12b, sil
0x14019def0  mov     [rsp+0F8h+arg_0], sil
0x14019def8  xor     r9d, r9d
0x14019defb  jmp     loc_14019DD5D
0x14019df00  test    dword ptr [r14+4], 4200000h
0x14019df08  jz      loc_14019DE32
0x14019df0e  test    rdi, rdi
0x14019df11  jz      short loc_14019DF1F
0x14019df13  cmp     dword ptr [rdi+100h], 80h
0x14019df1d  jz      short loc_14019DF30
0x14019df1f  test    dword ptr [r13+0B0h], 10000000h
0x14019df2a  jnz     loc_14019DE32
0x14019df30  cmp     r15, [r14+18h]
0x14019df34  jz      short loc_14019DF3F
0x14019df36  test    r15, r15
0x14019df39  jnz     loc_14019DE32
0x14019df3f  mov     rax, [rdx+8]
0x14019df43  mov     rcx, [rax+8]
0x14019df47  test    dword ptr [rcx+18h], 2000000h
0x14019df4e  jz      loc_14019EFA4
0x14019df54  and     dword ptr [rcx+14h], 0FFFFFFDFh
0x14019df58  mov     eax, [rsp+0F8h+arg_20]
0x14019df5f  and     eax, 0FFFFFFDFh
0x14019df62  mov     [rsp+0F8h+arg_20], eax
0x14019df69  jmp     loc_14019EFAB
0x14019df6e  mov     al, cs:NtfsStatusDebugFlags
0x14019df74  mov     r15d, 0C019003Fh
0x14019df7a  test    al, al
0x14019df7c  jz      short loc_14019DF8E
0x14019df7e  mov     r8d, 280B14h
0x14019df84  mov     edx, r15d
0x14019df87  xor     ecx, ecx
0x14019df89  call    NtfsStatusTraceAndDebugInternal
0x14019df8e  mov     [rsp+0F8h+var_A0], r15d
0x14019df93  jmp     loc_14019F1A4
0x14019df98  mov     al, cs:NtfsStatusDebugFlags
0x14019df9e  test    al, al
0x14019dfa0  jz      short loc_14019DFDF
0x14019dfa2  cmp     r15d, 0FFFFFFEDh
0x14019dfa6  jnb     short loc_14019DFDF
0x14019dfa8  cmp     r15d, 0C0000016h
0x14019dfaf  jz      short loc_14019DFDF
0x14019dfb1  cmp     r15d, 0C0000011h
0x14019dfb8  jz      short loc_14019DFDF
0x14019dfba  lea     eax, [r15+7FFFFFFBh]
0x14019dfc1  cmp     eax, esi
0x14019dfc3  jbe     short loc_14019DFDF
0x14019dfc5  cmp     r15d, 0C00000D8h
0x14019dfcc  jz      short loc_14019DFDF
0x14019dfce  mov     r8d, 280BDCh
0x14019dfd4  mov     edx, r15d
0x14019dfd7  mov     rcx, rbx
0x14019dfda  call    NtfsStatusTraceAndDebugInternal
0x14019dfdf  mov     ecx, r15d; Status
0x14019dfe2  call    cs:__imp_ExRaiseStatus
0x14019dfee  mov     al, cs:NtfsStatusDebugFlags
0x14019dff4  mov     ebx, 0C0190044h
0x14019dff9  test    al, al
0x14019dffb  jz      short loc_14019E00C
0x14019dffd  mov     r8d, 280C23h
0x14019e003  mov     edx, ebx
0x14019e005  xor     ecx, ecx
0x14019e007  call    NtfsStatusTraceAndDebugInternal
0x14019e00c  mov     [rsp+0F8h+var_A0], ebx
0x14019e010  mov     al, cs:NtfsStatusDebugFlags
0x14019e016  test    al, al
0x14019e018  jz      short loc_14019E029
0x14019e01a  mov     r8d, 280C23h
0x14019e020  mov     edx, ebx
0x14019e022  xor     ecx, ecx
0x14019e024  call    NtfsStatusTraceAndDebugInternal
0x14019e029  mov     ecx, ebx; Status
0x14019e02b  call    cs:__imp_ExRaiseStatus
0x14019e037  mov     al, cs:NtfsStatusDebugFlags
0x14019e03d  test    al, al
0x14019e03f  jz      short loc_14019E054
0x14019e041  mov     edx, 0C0000106h
0x14019e046  mov     r8d, 280CCDh
0x14019e04c  mov     rcx, rbx
0x14019e04f  call    NtfsStatusTraceAndDebugInternal
0x14019e054  mov     [rsp+0F8h+var_D8], 280CCDh
0x14019e05d  xor     r9d, r9d
0x14019e060  xor     r8d, r8d
0x14019e063  mov     edx, 0C0000106h
0x14019e068  mov     rcx, rbx
0x14019e06b  call    NtfsRaiseStatusInternal
0x14019e070  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x14019e077  call    cs:__imp_ExAllocateFromLookasideListEx
0x14019e07e  nop     dword ptr [rax+rax+00h]
0x14019e083  mov     r15, rax
0x14019e086  xor     edx, edx; Val
0x14019e088  lea     r8d, [rdx+50h]; Size
0x14019e08c  mov     rcx, rax; void *
0x14019e08f  call    memset
0x14019e094  movups  xmm0, xmmword ptr [r13+80h]
0x14019e09c  movups  xmmword ptr [r15+10h], xmm0
0x14019e0a1  movups  xmm1, xmmword ptr [r13+90h]
0x14019e0a9  movups  xmmword ptr [r15+20h], xmm1
0x14019e0ae  movups  xmm0, xmmword ptr [r13+0A0h]
0x14019e0b6  movups  xmmword ptr [r15+30h], xmm0
0x14019e0bb  movsd   xmm1, qword ptr [r13+0B0h]
0x14019e0c4  movsd   qword ptr [r15+40h], xmm1
0x14019e0ca  mov     eax, [r13+118h]
0x14019e0d1  mov     [r15+48h], eax
0x14019e0d5  lea     rax, [r14+58h]
0x14019e0d9  mov     rcx, [rax]
0x14019e0dc  cmp     [rcx+8], rax
0x14019e0e0  jz      short loc_14019E0E9
0x14019e0e2  mov     ecx, 3
0x14019e0e7  int     29h; Win8: RtlFailFast(ecx)
0x14019e0e9  mov     [r15], rcx
0x14019e0ec  mov     [r15+8], rax
0x14019e0f0  mov     [rcx+8], r15
0x14019e0f4  mov     [rax], r15
0x14019e0f7  or      dword ptr [r14+4], 8
0x14019e0fc  or      [r15+4Eh], si
0x14019e101  xor     r9d, r9d
0x14019e104  jmp     loc_14019EB81
0x14019e109  mov     rcx, [rsp+0F8h+var_98]
0x14019e10e  lea     rax, [rcx+140h]
0x14019e115  cmp     [rax], rax
0x14019e118  jz      short loc_14019E123
0x14019e11a  lock or dword ptr [r15+8], 100h
0x14019e123  mov     r15, [rsp+0F8h+arg_8]
0x14019e12b  mov     eax, [r15+18h]
0x14019e12f  test    al, 8
0x14019e131  jnz     short loc_14019E144
0x14019e133  mov     r9d, esi
0x14019e136  mov     r8, rdi
0x14019e139  mov     rdx, rcx
0x14019e13c  mov     rcx, rbx
0x14019e13f  call    TxfLogCurrentAttrSizesUndo
0x14019e144  mov     rcx, [r14+88h]; Resource
0x14019e14b  call    cs:__imp_ExReleaseResourceLite
0x14019e152  nop     dword ptr [rax+rax+00h]
0x14019e157  mov     [rsp+0F8h+arg_0], r12b
0x14019e15f  xor     r9d, r9d
0x14019e162  mov     r8b, sil
0x14019e165  mov     rdx, rdi
0x14019e168  mov     rcx, rbx
0x14019e16b  call    NtfsDeleteInternalAttributeStream
0x14019e170  mov     dl, sil; Wait
0x14019e173  mov     rcx, [r14+88h]; Resource
0x14019e17a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14019e181  nop     dword ptr [rax+rax+00h]
0x14019e186  mov     r12b, sil
0x14019e189  mov     [rsp+0F8h+arg_0], sil
0x14019e191  lock add [rdi+0D4h], esi
0x14019e198  mov     [rsp+0F8h+var_88], rdi
0x14019e19d  xor     eax, eax
0x14019e19f  cmp     [r15+70h], rax
0x14019e1a3  jnz     loc_14019E282
0x14019e1a9  cmp     [rdi+0D0h], eax
0x14019e1af  jz      short loc_14019E1BF
0x14019e1b1  mov     eax, [rdi+0D4h]
0x14019e1b7  sub     eax, esi
0x14019e1b9  cmp     eax, [r15+20h]
0x14019e1bd  ja      short loc_14019E1E0
0x14019e1bf  mov     rcx, [rdi+120h]
0x14019e1c6  add     rcx, 10h; SectionPointer
0x14019e1ca  xor     edx, edx; NewFileSize
0x14019e1cc  call    cs:__imp_MmCanFileBeTruncated
0x14019e1d3  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
