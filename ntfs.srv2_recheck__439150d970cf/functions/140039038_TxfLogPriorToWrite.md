# TxfLogPriorToWrite

- ea: `0x140039038`
- end: `0x140039e52`
- name: `TxfLogPriorToWrite`
- size: `3610`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400177d0`
- `0x14018a23c`
- `0x140268608`
- `0x140296da4`

## callees

- `0x140007ea0`
- `0x1400257c0`
- `0x140025830`
- `0x140039038`
- `0x14003b0d4`
- `0x14003ba34`
- `0x14003bb28`
- `0x140059250`
- `0x1400596c0`
- `0x1400f7e70`
- `0x1401000e0`
- `0x14010046c`
- `0x140100b14`
- `0x140100f30`
- `0x14010185c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140039df2`
- `ntoskrnl!KeReleaseMutex` at `0x14005bce0`
- `ntoskrnl!KeReleaseMutex` at `0x140039df2`
- `ntoskrnl!KeReleaseMutex` at `0x14005bce0`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140039d0e`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14005bbe8`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140039d0e`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14005bbe8`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140039712`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140039712`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140039dbf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005bcac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140039dbf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005bcac`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003967a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003967a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400395ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039ce8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005bbc2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400395ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039ce8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005bbc2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039636`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039d53`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bc34`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039636`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039d53`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bc34`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400396c6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140039cfb`
- `ntoskrnl!ExAcquireFastMutex` at `0x140039d7e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005bbd5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005bc63`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400396c6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140039cfb`
- `ntoskrnl!ExAcquireFastMutex` at `0x140039d7e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005bbd5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14005bc63`
- `ntoskrnl!ExReleaseFastMutex` at `0x140039728`
- `ntoskrnl!ExReleaseFastMutex` at `0x140039dd2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005bcc0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140039728`
- `ntoskrnl!ExReleaseFastMutex` at `0x140039dd2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005bcc0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140039c59`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140039c7f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14005bb1e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14005bb45`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140039c59`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140039c7f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14005bb1e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14005bb45`

## string_xrefs

- `0x140039918`: `TxfLogPriorToWrite`
- `0x1400399bf`: `TxfLogPriorToWrite`

## pseudocode

```c
__int64 __fastcall TxfLogPriorToWrite(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8)
{
  __int64 v11; // r14
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rcx
  int v15; // edx
  int v16; // edx
  _DWORD *v17; // rdi
  __int64 v19; // rax
  unsigned int v20; // r8d
  ULONG v21; // r15d
  unsigned int v22; // esi
  __int64 v23; // r9
  __int64 v24; // rdi
  __int64 v25; // r8
  unsigned __int64 v26; // r15
  __int64 v27; // rcx
  int v28; // ecx
  signed __int64 v29; // rdi
  signed __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rcx
  unsigned __int64 v34; // r12
  __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  char v37; // r10
  unsigned int *v38; // r15
  __int64 v39; // rdi
  unsigned __int64 v40; // rdi
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rdi
  unsigned __int64 v43; // r13
  bool v44; // r15
  unsigned int v45; // r9d
  __int64 v46; // r15
  int v47; // r10d
  int TopsRange; // r10d
  unsigned __int64 v49; // r8
  __int64 v50; // r15
  unsigned __int64 v51; // r9
  bool v52; // r11
  __int64 v53; // rcx
  _QWORD *v54; // r10
  BOOL v55; // r9d
  __int64 v56; // rdx
  ULONG v57; // eax
  BOOLEAN v58; // al
  __int64 v59; // r14
  _QWORD *v60; // rax
  __int64 v61; // rcx
  _QWORD *v62; // rdx
  _QWORD *v63; // rdx
  char v64; // [rsp+80h] [rbp-2A8h]
  bool v65; // [rsp+81h] [rbp-2A7h]
  char v66; // [rsp+82h] [rbp-2A6h]
  unsigned int v67; // [rsp+84h] [rbp-2A4h]
  ULONG Length; // [rsp+88h] [rbp-2A0h]
  int v69; // [rsp+90h] [rbp-298h]
  __int16 v70; // [rsp+94h] [rbp-294h] BYREF
  unsigned int v71; // [rsp+98h] [rbp-290h] BYREF
  unsigned int v72; // [rsp+9Ch] [rbp-28Ch]
  int v73; // [rsp+A0h] [rbp-288h]
  int v74[2]; // [rsp+A8h] [rbp-280h] BYREF
  union _LARGE_INTEGER v75; // [rsp+B0h] [rbp-278h] BYREF
  int v76; // [rsp+B8h] [rbp-270h]
  __int64 v77; // [rsp+C0h] [rbp-268h]
  unsigned int v78; // [rsp+C8h] [rbp-260h]
  __int64 v79; // [rsp+D0h] [rbp-258h]
  int v80[2]; // [rsp+D8h] [rbp-250h]
  __int64 v81; // [rsp+E0h] [rbp-248h]
  unsigned __int64 v82; // [rsp+E8h] [rbp-240h]
  __int64 v83; // [rsp+F0h] [rbp-238h]
  __int64 v84; // [rsp+F8h] [rbp-230h]
  ULONG DeleteCount; // [rsp+100h] [rbp-228h] BYREF
  int v86; // [rsp+104h] [rbp-224h]
  PVOID RestartKey; // [rsp+108h] [rbp-220h] BYREF
  unsigned __int64 v88; // [rsp+110h] [rbp-218h]
  __int64 v89; // [rsp+118h] [rbp-210h]
  unsigned __int64 v90; // [rsp+120h] [rbp-208h]
  __int64 v91; // [rsp+128h] [rbp-200h]
  int v92[2]; // [rsp+130h] [rbp-1F8h]
  _QWORD *v93; // [rsp+138h] [rbp-1F0h]
  __int64 v94; // [rsp+140h] [rbp-1E8h]
  __int64 v95; // [rsp+150h] [rbp-1D8h]
  _QWORD *v96; // [rsp+158h] [rbp-1D0h]
  unsigned __int64 v97; // [rsp+160h] [rbp-1C8h]
  _QWORD v98[8]; // [rsp+170h] [rbp-1B8h] BYREF
  _QWORD MatchData[38]; // [rsp+1B0h] [rbp-178h] BYREF

  v91 = a4;
  *(_QWORD *)v92 = a2;
  *(_QWORD *)v80 = a1;
  v84 = a3;
  v11 = 0;
  v75.QuadPart = 0;
  memset(MatchData, 0, 0x124u);
  DeleteCount = 0;
  RestartKey = 0;
  v12 = *(_QWORD *)(a2 + 24);
  v77 = v12;
  v79 = *(_QWORD *)(v12 + 184);
  v13 = *(_QWORD *)(v79 + 320);
  v83 = v13;
  v70 = 0;
  *(_QWORD *)v74 = 0;
  memset(v98, 0, sizeof(v98));
  v14 = *(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL);
  v15 = *(_DWORD *)(*(_QWORD *)(v14 + 24) + 16LL);
  if ( (v15 & 0x9000000) == 0 || (v15 & 0x80000) != 0 )
  {
    v16 = 0;
    *(_DWORD *)(v14 + 4) |= 0x2000u;
  }
  else
  {
    v16 = 1;
  }
  v69 = v16;
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 4LL) & 0x1000) != 0
    || (*(_DWORD *)(v13 + 128) & 0x20000000) != 0 )
  {
    return 0;
  }
  v66 = 0;
  if ( v16 )
  {
    v17 = (_DWORD *)(a3 + 8);
    if ( (*(_DWORD *)(a3 + 8) & 0x10) == 0 )
    {
      if ( a6 )
      {
        if ( (*(_DWORD *)(a6 + 16) & 2) != 0 )
        {
          v11 = NtfsMapUserBufferNoRaise(a6, 1073741856);
          if ( v11 )
          {
LABEL_18:
            v16 = v69;
            goto LABEL_21;
          }
          if ( a5 > 4096 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221225495LL, 3408815);
            return 3221225495LL;
          }
          v98[0] = 0;
          LODWORD(v98[1]) = 64;
          v98[4] = 0;
          v98[5] = 0x2000;
          v19 = NtfsReservedMapBuffer(*(_QWORD *)(v12 + 192) + 5448LL, *(_QWORD *)(a6 + 8), v98, 0, a5);
          v66 = 1;
        }
        else
        {
          v19 = NtfsMapUserBuffer(a6, 16);
        }
        v11 = v19;
        goto LABEL_18;
      }
    }
  }
  v17 = (_DWORD *)(a3 + 8);
LABEL_21:
  v89 = v83;
  v20 = 0;
  v67 = 0;
  v76 = 0;
  v21 = 0;
  Length = 0;
  v72 = 0;
  v93 = MatchData;
  v94 = v83 + 280;
  v73 = 0;
  v95 = v77;
  v96 = v98;
  v78 = 0;
  v22 = 0;
  v71 = 0;
  v23 = a5;
  v81 = a5;
  if ( (*v17 & 4) != 0 )
  {
    if ( v11 )
    {
      TxfDoWriteFileLogging(v80[0], a3, v79, v11, a4, a5, 0, v16, a8);
      v20 = 0;
    }
LABEL_122:
    v24 = v77;
    goto LABEL_123;
  }
  v24 = v77;
  v25 = *(_QWORD *)(v77 + 32);
  v26 = a5 + a4;
  if ( a5 + a4 <= v25 )
  {
    v27 = a5;
LABEL_33:
    if ( a7 && *(_BYTE *)(v77 + 460) )
    {
      v28 = *(_DWORD *)(v77 + 452);
      v29 = a4 & -v28;
      v90 = v29;
      v30 = -v28 & (unsigned __int64)(a4 + v23 + v28 - 1);
      if ( v30 <= v25 )
        v31 = v30 - v29;
      else
        v31 = v25 - v29;
    }
    else
    {
      v29 = a4;
      v31 = v27;
    }
    v32 = *(_QWORD *)(a3 + 96);
    if ( v31 + v29 <= v32 )
    {
      v33 = v31;
    }
    else
    {
      if ( a4 < (unsigned __int64)v32 )
      {
        if ( v26 > v32 )
        {
          if ( v11 )
            TxfDoWriteFileLogging(v80[0], a3, v79, v11 + *(_DWORD *)(a3 + 96) - a4, v32, v26 - v32, 0, v69, a8);
          v32 = *(_QWORD *)(a3 + 96);
          v81 = v32 - a4;
        }
      }
      else
      {
        if ( v11 )
          TxfDoWriteFileLogging(v80[0], a3, v79, v11, a4, v23, 0, v69, a8);
        v32 = *(_QWORD *)(a3 + 96);
        if ( v29 >= v32 )
        {
LABEL_89:
          v20 = v67;
LABEL_121:
          v21 = Length;
          goto LABEL_122;
        }
      }
      v33 = v32 - v29;
    }
    v90 = v29 & 0xFFFFFFFFFFFFF000uLL;
    v34 = ((v29 + v33 + 4095) & 0xFFFFFFFFFFFFF000uLL) - (v29 & 0xFFFFFFFFFFFFF000uLL);
    *(_QWORD *)v74 = v29 & 0xFFFFFFFFFFFFF000uLL;
    v88 = v34;
    ExAcquireResourceExclusiveLite(
      (PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 24LL) + 24LL) + 80LL),
      1u);
    v35 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 24LL);
    v65 = *(_QWORD *)(v35 + 320) != v35 + 320 || (*(_DWORD *)(v35 + 16) & 0x400) != 0;
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v35 + 24) + 80LL));
    v36 = *(_QWORD *)v74;
    v37 = 0;
    while ( 1 )
    {
      if ( v37 && !v73 )
      {
        KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(a3 + 16) + 120LL), Executive, 0, 0, 0);
        v73 = 1;
        v36 = *(_QWORD *)v74;
      }
      MatchData[0] = v36 >> 12;
      LODWORD(MatchData[3]) = v34 >> 12;
      RestartKey = 0;
      ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
      v38 = (unsigned int *)RtlEnumerateGenericTableLikeADirectory(
                              (PRTL_AVL_TABLE)(a3 + 152),
                              TxfMatchPageRange,
                              MatchData,
                              0,
                              &RestartKey,
                              &DeleteCount,
                              MatchData);
      ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
      if ( !v38 )
        break;
      v39 = *(_QWORD *)v38;
      v36 = *(_QWORD *)v74;
      if ( *(_QWORD *)v38 <= MatchData[0] )
      {
        v42 = (v38[6] + v39) << 12;
        if ( v34 + *(_QWORD *)v74 <= v42 )
        {
          v40 = v34;
          v82 = v34;
          v41 = v34;
        }
        else
        {
          v40 = v42 - *(_QWORD *)v74;
          v82 = v40;
          v41 = v40;
        }
        v37 = 0;
        v64 = 0;
LABEL_68:
        v43 = v91;
        v20 = 0;
LABEL_69:
        if ( v41 )
        {
          if ( v37 || v11 && v69 )
          {
            v44 = v65;
LABEL_76:
            v20 = v40;
            v67 = v40;
            v76 = v40;
            if ( ((v36 ^ (v36 + (unsigned int)v40 - 1LL)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
            {
              v20 = 0x40000 - (v36 & 0x3FFFE);
              v67 = v20;
              v76 = v20;
            }
            while ( 1 )
            {
              if ( v37 || v44 )
              {
                if ( !v22 )
                {
                  v46 = *(_QWORD *)v80;
                  v47 = TxfCheckQuotaForTopsAllocation(*(_QWORD *)v80, v79, a3, v20);
                  v78 = v47;
                  v86 = v47;
                  if ( v47 < 0 )
                  {
                    if ( (*(_DWORD *)(*(_QWORD *)(v46 + 112) + 16LL) & 2) != 0 )
                      TxfRaiseAndAbortAtTopLevelPriv(
                        v46,
                        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 24LL),
                        0,
                        0,
                        1,
                        v47,
                        (__int64)"TxfLogPriorToWrite",
                        (__int64)"TxfStreamSup.c",
                        1563);
                    goto LABEL_89;
                  }
                  TopsRange = TxfAllocateTopsRange(v46, v79, a3, v67, (__int64)&v75, (__int64)&v71, (__int64)&v70);
                  v78 = TopsRange;
                  v86 = TopsRange;
                  if ( TopsRange < 0 )
                  {
                    if ( (*(_DWORD *)(*(_QWORD *)(v46 + 112) + 16LL) & 2) != 0 )
                      TxfRaiseAndAbortAtTopLevelPriv(
                        v46,
                        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 24LL),
                        0,
                        0,
                        1,
                        TopsRange,
                        (__int64)"TxfLogPriorToWrite",
                        (__int64)"TxfStreamSup.c",
                        1606);
                    v22 = v71;
                    goto LABEL_89;
                  }
                  v22 = v71;
                  v36 = *(_QWORD *)v74;
                  v37 = v64;
                }
                v45 = v22;
                Length = v22;
                v72 = v22;
                if ( ((v75.QuadPart ^ (v22 + v75.QuadPart - 1)) & 0xFFFFFFFFFFFF0000uLL) != 0 )
                {
                  v45 = 0x10000 - LOWORD(v75.LowPart);
                  Length = v45;
                  v72 = v45;
                }
              }
              else
              {
                v45 = v20;
                Length = v20;
                v72 = v20;
              }
              v49 = v36;
              if ( v36 < v43 )
                v49 = v43;
              v97 = v49;
              v50 = v45;
              v51 = v45 + v36;
              v52 = v49 >= v43 + v81;
              if ( v49 >= v51 )
                v52 = 1;
              if ( v49 + v50 <= v43 + v81 )
                v53 = v50;
              else
                v53 = v81 + v43 - v49;
              if ( v49 + v53 > v51 )
                v53 = v36 + v50 - v49;
              if ( v37 || v65 )
                v54 = MatchData;
              else
                v54 = 0;
              v55 = v64 && !*(_QWORD *)(a3 + 112);
              if ( !v11 || v52 )
                v56 = 0;
              else
                v56 = v11 + (unsigned int)(v49 - v43);
              TxfLogOldStreamData(
                v80[0],
                v92[0],
                a3,
                (int)v74,
                &v75,
                Length,
                v56,
                v49,
                v53,
                a7,
                v69,
                v55,
                a8,
                v70,
                0,
                v54);
              v37 = v64;
              if ( v64 || v65 )
              {
                v75.QuadPart += v50;
                v57 = Length;
                v22 -= Length;
                v71 = v22;
              }
              else
              {
                v57 = Length;
              }
              v36 = v50 + *(_QWORD *)v74;
              *(_QWORD *)v74 += v50;
              v20 = v67 - v57;
              v67 = v20;
              v76 = v20;
              v40 -= v50;
              v82 = v40;
              v41 = v40;
              v34 -= v50;
              v88 = v34;
              v44 = v65;
              if ( !v20 )
                goto LABEL_69;
            }
          }
          v44 = v65;
          if ( v65 )
            goto LABEL_76;
          v36 += v41;
          *(_QWORD *)v74 = v36;
          v34 -= v41;
          v88 = v34;
        }
        if ( !v34 )
          goto LABEL_121;
      }
      else
      {
        v40 = (v39 << 12) - *(_QWORD *)v74;
        v82 = v40;
        v37 = 1;
        v41 = v40;
LABEL_67:
        v64 = 1;
        if ( v73 )
          goto LABEL_68;
      }
    }
    v40 = v34;
    v82 = v34;
    v41 = v34;
    v37 = 1;
    v36 = *(_QWORD *)v74;
    goto LABEL_67;
  }
  if ( a4 < v25 )
  {
    if ( v11 )
    {
      TxfDoWriteFileLogging(v80[0], a3, v79, v11 + *(_DWORD *)(v77 + 32) - a4, v25, v26 - v25, 0, v16, a8);
      v23 = v81;
    }
    v25 = *(_QWORD *)(v77 + 32);
    v27 = v25 - a4;
    goto LABEL_33;
  }
  if ( v11 )
    TxfDoWriteFileLogging(v80[0], a3, v79, v11, a4, a5, 0, v16, a8);
  v20 = 0;
  v21 = 0;
LABEL_123:
  if ( v22 )
  {
    if ( !ClfsLsnInvalid((const CLFS_LSN *)&MatchData[2]) )
    {
      v75.QuadPart += v21;
      v22 -= v21;
    }
    v58 = ClfsLsnInvalid((const CLFS_LSN *)&MatchData[2]);
    v59 = v83;
    if ( v58 && (MatchData[3] & 0x2000000000000LL) == 0 )
      TxfRemoveTopsRange(*(_QWORD *)(v83 + 16), a3, MatchData[1], LODWORD(MatchData[3]));
    if ( v22 )
      TxfFreeTopsRange(v59, a3, (unsigned int)&v75, v22, 15);
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v59 + 368), 1u);
    ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    if ( RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(a3 + 152)) && !*(_QWORD *)(a3 + 288) )
    {
      v60 = (_QWORD *)(a3 + 48);
      v61 = *(_QWORD *)(a3 + 48);
      if ( *(_QWORD *)(v61 + 8) != a3 + 48 || (v62 = *(_QWORD **)(a3 + 56), (_QWORD *)*v62 != v60) )
        __fastfail(3u);
      *v62 = v61;
      *(_QWORD *)(v61 + 8) = v62;
      *v60 = 0;
    }
    ExReleaseResourceLite(*(PERESOURCE *)(v59 + 368));
  }
  else
  {
    if ( v20 && *(_QWORD *)(a3 + 296) )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
      v22 = 1;
    }
    if ( !v22 )
      goto LABEL_147;
  }
  v63 = *(_QWORD **)(a3 + 296);
  if ( v63 && !v63[1] && !v63[2] )
  {
    *(_QWORD *)(a3 + 296) = v63[3];
    ExFreeToLookasideListEx(&TxfVscbQuotaInfoLookasideList, v63);
  }
  ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
LABEL_147:
  if ( v73 )
    KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(a3 + 16) + 120LL), 0);
  if ( v66 )
    NtfsReservedUnmapBuffer(*(_QWORD *)(v24 + 192) + 5448LL, v98);
  return v78;
}

```

## disassembly

```asm
0x140039038  push    rbx
0x14003903a  push    rsi
0x14003903b  push    rdi
0x14003903c  push    r12
0x14003903e  push    r13
0x140039040  push    r14
0x140039042  push    r15
0x140039044  sub     rsp, 2F0h
0x14003904b  mov     rax, cs:__security_cookie
0x140039052  xor     rax, rsp
0x140039055  mov     [rsp+328h+var_48], rax
0x14003905d  mov     r12, r9
0x140039060  mov     [rsp+328h+var_200], r9
0x140039068  mov     rbx, r8
0x14003906b  mov     rdi, rdx
0x14003906e  mov     qword ptr [rsp+328h+var_1F8], rdx
0x140039076  mov     qword ptr [rsp+328h+var_250], rcx
0x14003907e  mov     [rsp+328h+var_230], rbx
0x140039086  mov     rsi, [rsp+328h+arg_28]
0x14003908e  xor     r14d, r14d
0x140039091  mov     qword ptr [rsp+328h+var_278], r14
0x140039099  xor     edx, edx; Val
0x14003909b  mov     r8d, 124h; Size
0x1400390a1  lea     rcx, [rsp+328h+MatchData]; void *
0x1400390a9  call    memset
0x1400390ae  mov     [rsp+328h+var_228], r14d
0x1400390b6  mov     [rsp+328h+RestartKey], r14
0x1400390be  mov     r15, [rdi+18h]
0x1400390c2  mov     [rsp+328h+var_268], r15
0x1400390ca  mov     rax, [r15+0B8h]
0x1400390d1  mov     [rsp+328h+var_258], rax
0x1400390d9  mov     rdi, [rax+140h]
0x1400390e0  mov     [rsp+328h+var_238], rdi
0x1400390e8  mov     [rsp+328h+var_294], r14w
0x1400390f1  mov     qword ptr [rsp+328h+var_280], r14
0x1400390f9  xor     edx, edx; Val
0x1400390fb  lea     r8d, [r14+40h]; Size
0x1400390ff  lea     rcx, [rsp+328h+var_1B8]; void *
0x140039107  call    memset
0x14003910c  mov     rax, [rbx+10h]
0x140039110  mov     rcx, [rax+40h]
0x140039114  mov     rax, [rcx+18h]
0x140039118  mov     edx, [rax+10h]
0x14003911b  test    edx, 9000000h
0x140039121  jz      short loc_140039132
0x140039123  bt      edx, 13h
0x140039127  jb      short loc_140039132
0x140039129  lea     r13d, [r14+1]
0x14003912d  mov     edx, r13d
0x140039130  jmp     short loc_140039140
0x140039132  mov     edx, r14d
0x140039135  bts     dword ptr [rcx+4], 0Dh
0x14003913a  mov     r13d, 1
0x140039140  mov     [rsp+328h+var_298], edx
0x140039147  mov     rax, [rbx+10h]
0x14003914b  mov     rcx, [rax+40h]
0x14003914f  test    dword ptr [rcx+4], 1000h
0x140039156  jnz     loc_140039E2C
0x14003915c  test    dword ptr [rdi+80h], 20000000h
0x140039166  jnz     loc_140039E2C
0x14003916c  mov     [rsp+328h+var_2A6], r14b
0x140039174  test    edx, edx
0x140039176  jz      loc_14003925F
0x14003917c  lea     rdi, [rbx+8]
0x140039180  mov     eax, [rdi]
0x140039182  test    al, 10h
0x140039184  jnz     loc_14003925F
0x14003918a  test    rsi, rsi
0x14003918d  jz      loc_14003925F
0x140039193  mov     eax, [rsi+10h]
0x140039196  mov     rcx, rsi
0x140039199  test    al, 2
0x14003919b  jz      loc_140039253
0x1400391a1  mov     edx, 40000020h
0x1400391a6  call    NtfsMapUserBufferNoRaise
0x1400391ab  mov     r14, rax
0x1400391ae  xor     ecx, ecx
0x1400391b0  test    rax, rax
0x1400391b3  jnz     loc_14003924A
0x1400391b9  cmp     [rsp+328h+arg_20], 1000h
0x1400391c5  jle     short loc_1400391EB
0x1400391c7  mov     al, cs:NtfsStatusDebugFlags
0x1400391cd  test    al, al
0x1400391cf  jz      short loc_1400391E1
0x1400391d1  mov     edx, 0C0000017h
0x1400391d6  mov     r8d, 3403AFh
0x1400391dc  call    NtfsStatusTraceAndDebugInternal
0x1400391e1  mov     eax, 0C0000017h
0x1400391e6  jmp     loc_140039E2E
0x1400391eb  mov     [rsp+328h+var_1B8], rcx
0x1400391f3  mov     [rsp+328h+var_1B0], 40h ; '@'
0x1400391fe  mov     [rsp+328h+var_198], rcx
0x140039206  mov     [rsp+328h+var_190], 2000h
0x140039212  mov     rcx, [r15+0C0h]
0x140039219  add     rcx, 1548h
0x140039220  mov     eax, dword ptr [rsp+328h+arg_20]
0x140039227  mov     dword ptr [rsp+328h+Timeout], eax
0x14003922b  xor     r9d, r9d
0x14003922e  lea     r8, [rsp+328h+var_1B8]
0x140039236  mov     rdx, [rsi+8]
0x14003923a  call    NtfsReservedMapBuffer
0x14003923f  mov     [rsp+328h+var_2A6], r13b
0x140039247  mov     r14, rax
0x14003924a  mov     edx, [rsp+328h+var_298]
0x140039251  jmp     short loc_140039263
0x140039253  mov     edx, 10h
0x140039258  call    NtfsMapUserBuffer
0x14003925d  jmp     short loc_140039247
0x14003925f  lea     rdi, [rbx+8]
0x140039263  mov     rax, [rsp+328h+var_238]
0x14003926b  mov     [rsp+328h+var_210], rax
0x140039273  xor     r8d, r8d
0x140039276  mov     [rsp+328h+var_2A4], r8d
0x14003927e  mov     [rsp+328h+var_270], r8d
0x140039286  xor     r15d, r15d
0x140039289  mov     [rsp+328h+Length], r15d
0x140039291  mov     [rsp+328h+var_28C], r15d
0x140039299  lea     rcx, [rsp+328h+MatchData]
0x1400392a1  mov     [rsp+328h+var_1F0], rcx
0x1400392a9  add     rax, 118h
0x1400392af  mov     [rsp+328h+var_1E8], rax
0x1400392b7  xor     al, al
0x1400392b9  mov     [rsp+328h+var_2A8], al
0x1400392c0  mov     [rsp+328h+var_288], r8d
0x1400392c8  mov     rax, [rsp+328h+var_268]
0x1400392d0  mov     [rsp+328h+var_1D8], rax
0x1400392d8  lea     rax, [rsp+328h+var_1B8]
0x1400392e0  mov     [rsp+328h+var_1D0], rax
0x1400392e8  mov     [rsp+328h+var_260], r8d
0x1400392f0  xor     esi, esi
0x1400392f2  mov     [rsp+328h+var_290], esi
0x1400392f9  mov     r9, [rsp+328h+arg_20]
0x140039301  mov     [rsp+328h+var_248], r9
0x140039309  mov     eax, [rdi]
0x14003930b  test    al, 4
0x14003930d  jz      short loc_14003935E
0x14003930f  test    r14, r14
0x140039312  jz      loc_140039C41
0x140039318  mov     eax, [rsp+328h+arg_38]
0x14003931f  mov     dword ptr [rsp+328h+var_2E8], eax
0x140039323  mov     dword ptr [rsp+328h+var_2F0], edx
0x140039327  mov     [rsp+328h+Buffer], rsi
0x14003932c  mov     [rsp+328h+DeleteCount], r9
0x140039331  mov     [rsp+328h+Timeout], r12
0x140039336  mov     r9, r14
0x140039339  mov     r8, [rsp+328h+var_258]
0x140039341  mov     rdx, rbx
0x140039344  mov     rcx, qword ptr [rsp+328h+var_250]
0x14003934c  call    TxfDoWriteFileLogging
0x140039351  mov     r8d, [rsp+328h+var_2A4]
0x140039359  jmp     loc_140039C41
0x14003935e  mov     rdi, [rsp+328h+var_268]
0x140039366  mov     r8, [rdi+20h]
0x14003936a  lea     r15, [r9+r12]
0x14003936e  cmp     r15, r8
0x140039371  jle     loc_140039446
0x140039377  cmp     r12, r8
0x14003937a  jl      short loc_1400393DB
0x14003937c  test    r14, r14
0x14003937f  jz      short loc_1400393C6
0x140039381  mov     eax, [rsp+328h+arg_38]
0x140039388  mov     dword ptr [rsp+328h+var_2E8], eax
0x14003938c  mov     dword ptr [rsp+328h+var_2F0], edx
0x140039390  mov     [rsp+328h+Buffer], 0
0x140039399  mov     rax, [rsp+328h+arg_20]
0x1400393a1  mov     [rsp+328h+DeleteCount], rax
0x1400393a6  mov     [rsp+328h+Timeout], r12
0x1400393ab  mov     r9, r14
0x1400393ae  mov     r8, [rsp+328h+var_258]
0x1400393b6  mov     rdx, rbx
0x1400393b9  mov     rcx, qword ptr [rsp+328h+var_250]
0x1400393c1  call    TxfDoWriteFileLogging
0x1400393c6  mov     r8d, [rsp+328h+var_2A4]
0x1400393ce  mov     r15d, [rsp+328h+Length]
0x1400393d6  jmp     loc_140039C49
0x1400393db  test    r14, r14
0x1400393de  jz      short loc_140039432
0x1400393e0  mov     rcx, r15
0x1400393e3  sub     rcx, r8
0x1400393e6  mov     r9d, [rdi+20h]
0x1400393ea  sub     r9d, r12d
0x1400393ed  add     r9, r14
0x1400393f0  mov     eax, [rsp+328h+arg_38]
0x1400393f7  mov     dword ptr [rsp+328h+var_2E8], eax
0x1400393fb  mov     dword ptr [rsp+328h+var_2F0], edx
0x1400393ff  mov     [rsp+328h+Buffer], 0
0x140039408  mov     [rsp+328h+DeleteCount], rcx
0x14003940d  mov     [rsp+328h+Timeout], r8
0x140039412  mov     r8, [rsp+328h+var_258]
0x14003941a  mov     rdx, rbx
0x14003941d  mov     rcx, qword ptr [rsp+328h+var_250]
0x140039425  call    TxfDoWriteFileLogging
0x14003942a  mov     r9, [rsp+328h+var_248]
0x140039432  mov     r8, [rdi+20h]
0x140039436  mov     rcx, r8
0x140039439  sub     rcx, r12
0x14003943c  mov     [rsp+328h+arg_20], rcx
0x140039444  jmp     short loc_140039449
0x140039446  mov     rcx, r9
0x140039449  cmp     [rsp+328h+arg_30], 0
0x140039451  jz      short loc_1400394AB
0x140039453  cmp     byte ptr [rdi+1CCh], 0
0x14003945a  jz      short loc_1400394AB
0x14003945c  mov     ecx, [rdi+1C4h]
0x140039462  mov     eax, ecx
0x140039464  neg     eax
0x140039466  movsxd  rdx, eax
0x140039469  mov     rdi, rdx
0x14003946c  and     rdi, r12
0x14003946f  mov     [rsp+328h+var_208], rdi
0x140039477  lea     eax, [rcx-1]
0x14003947a  movsxd  rcx, eax
0x14003947d  add     rcx, r9
0x140039480  add     rcx, r12
0x140039483  and     rcx, rdx
0x140039486  mov     rax, rcx
0x140039489  sub     rax, rdi
0x14003948c  mov     [rsp+328h+arg_20], rax
0x140039494  cmp     rcx, r8
0x140039497  jle     short loc_1400394A6
0x140039499  sub     r8, rdi
0x14003949c  mov     [rsp+328h+arg_20], r8
0x1400394a4  jmp     short loc_1400394B1
0x1400394a6  mov     r8, rax
0x1400394a9  jmp     short loc_1400394B1
0x1400394ab  mov     rdi, r12
0x1400394ae  mov     r8, rcx
0x1400394b1  mov     rcx, [rbx+60h]
0x1400394b5  lea     rax, [r8+rdi]
0x1400394b9  cmp     rax, rcx
0x1400394bc  jle     loc_140039595
0x1400394c2  cmp     r12, rcx
0x1400394c5  jb      short loc_14003951E
0x1400394c7  test    r14, r14
0x1400394ca  jz      short loc_140039510
0x1400394cc  mov     eax, [rsp+328h+arg_38]
0x1400394d3  mov     dword ptr [rsp+328h+var_2E8], eax
0x1400394d7  mov     eax, [rsp+328h+var_298]
0x1400394de  mov     dword ptr [rsp+328h+var_2F0], eax
0x1400394e2  mov     [rsp+328h+Buffer], 0
0x1400394eb  mov     [rsp+328h+DeleteCount], r9
0x1400394f0  mov     [rsp+328h+Timeout], r12
0x1400394f5  mov     r9, r14
0x1400394f8  mov     r8, [rsp+328h+var_258]
0x140039500  mov     rdx, rbx
0x140039503  mov     rcx, qword ptr [rsp+328h+var_250]
0x14003950b  call    TxfDoWriteFileLogging
0x140039510  mov     rcx, [rbx+60h]
0x140039514  cmp     rdi, rcx
0x140039517  jl      short loc_140039588
0x140039519  jmp     loc_1400399EE
0x14003951e  cmp     r15, rcx
0x140039521  jbe     short loc_140039588
0x140039523  test    r14, r14
0x140039526  jz      short loc_140039576
0x140039528  sub     r15, rcx
0x14003952b  mov     r9d, [rbx+60h]
0x14003952f  sub     r9d, r12d
0x140039532  add     r9, r14
0x140039535  mov     eax, [rsp+328h+arg_38]
0x14003953c  mov     dword ptr [rsp+328h+var_2E8], eax
0x140039540  mov     eax, [rsp+328h+var_298]
0x140039547  mov     dword ptr [rsp+328h+var_2F0], eax
0x14003954b  mov     [rsp+328h+Buffer], 0
0x140039554  mov     [rsp+328h+DeleteCount], r15
0x140039559  mov     [rsp+328h+Timeout], rcx
0x14003955e  mov     r8, [rsp+328h+var_258]
0x140039566  mov     rdx, rbx
0x140039569  mov     rcx, qword ptr [rsp+328h+var_250]
0x140039571  call    TxfDoWriteFileLogging
0x140039576  mov     rcx, [rbx+60h]
0x14003957a  mov     rax, rcx
0x14003957d  sub     rax, r12
0x140039580  mov     [rsp+328h+var_248], rax
0x140039588  sub     rcx, rdi
0x14003958b  mov     [rsp+328h+arg_20], rcx
0x140039593  jmp     short loc_140039598
0x140039595  mov     rcx, r8
0x140039598  mov     rax, rdi
0x14003959b  mov     rdx, 0FFFFFFFFFFFFF000h
0x1400395a2  and     rax, rdx
0x1400395a5  mov     [rsp+328h+var_208], rax
0x1400395ad  lea     r12, [rcx+0FFFh]
0x1400395b4  add     r12, rdi
0x1400395b7  and     r12, rdx
0x1400395ba  sub     r12, rax
0x1400395bd  mov     [rsp+328h+arg_20], r12
0x1400395c5  mov     qword ptr [rsp+328h+var_280], rax
0x1400395cd  mov     [rsp+328h+var_218], r12
0x1400395d5  mov     rax, [rbx+10h]
0x1400395d9  mov     rcx, [rax+40h]
0x1400395dd  mov     rax, [rcx+18h]
0x1400395e1  mov     rcx, [rax+18h]
0x1400395e5  add     rcx, 50h ; 'P'; Resource
0x1400395e9  mov     dl, r13b; Wait
0x1400395ec  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400395f3  nop     dword ptr [rax+rax+00h]
0x1400395f8  mov     rax, [rbx+10h]
0x1400395fc  mov     rcx, [rax+40h]
0x140039600  mov     rcx, [rcx+18h]
  ... truncated ...
```
