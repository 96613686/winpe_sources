# NtfsRenameToPrivateDir

- ea: `0x1401493f4`
- end: `0x14014a7c8`
- name: `NtfsRenameToPrivateDir`
- size: `5076`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `reparse_path, installer_update`

## callers

- `0x1401c3700`
- `0x140227518`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x14000ea70`
- `0x14000eaa0`
- `0x140012e10`
- `0x140012e70`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x1401216d0`
- `0x14012ba70`
- `0x14012f930`
- `0x140140380`
- `0x1401493f4`
- `0x14014a7d0`
- `0x14014a930`
- `0x14014b5a8`
- `0x14014bae0`
- `0x140154138`
- `0x140154d10`
- `0x1401633d0`
- `0x1401990f0`
- `0x1401e0660`
- `0x1401e3230`
- `0x1402192f0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401496f8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401496f8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401496dd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140149848`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401496dd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140149848`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x14014a240`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x14014a240`
- `ntoskrnl!RtlRandomEx` at `0x1401497df`
- `ntoskrnl!RtlRandomEx` at `0x1401497df`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x14014a3a1`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x14014a3a1`
- `ntoskrnl!FsRtlLegalAnsiCharacterArray` at `0x1401498d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140149a36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a710`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a72e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a744`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a767`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7a55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140149a36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a6f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a710`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a72e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a744`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014a767`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a79fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7a55`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140149640`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140149665`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140149a7d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014a003`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014a552`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140149640`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140149665`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140149a7d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014a003`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014a552`
- `ntoskrnl!CcUnpinData` at `0x14014a591`
- `ntoskrnl!CcUnpinData` at `0x14014a591`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14014a105`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14014a105`

## pseudocode

```c
__int64 __fastcall NtfsRenameToPrivateDir(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        void *a8)
{
  __int64 v10; // r14
  int v11; // eax
  __int64 v12; // r12
  __int64 v13; // r13
  int v14; // esi
  USHORT v15; // bx
  char v16; // r14
  signed __int64 v17; // r9
  PWSTR Buffer; // rbx
  PWSTR v19; // r10
  unsigned int v20; // r8d
  unsigned int i; // edx
  __int64 v22; // rcx
  ULONG v23; // eax
  int j; // r8d
  __int64 v25; // rdx
  __int64 v26; // r8
  char v27; // r11
  char v28; // r9
  unsigned int v29; // ebx
  unsigned int v30; // r10d
  __int64 v31; // rbx
  unsigned int v32; // ebx
  unsigned int v33; // eax
  unsigned __int16 v34; // bx
  _WORD *v35; // r14
  __int64 v36; // rbx
  char IndexEntry; // al
  int v38; // ecx
  _QWORD *v39; // rax
  _DWORD *v40; // rbx
  __int64 v41; // r9
  __int64 v42; // rbx
  bool v43; // r14
  __int64 v44; // r9
  char v45; // r9
  PVOID v46; // r14
  __int64 v47; // rdx
  __int64 v48; // rax
  _QWORD *k; // rcx
  _QWORD *v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // rbx
  unsigned int v53; // r12d
  __int64 v54; // rsi
  unsigned int v55; // esi
  char *PoolWithTag; // rbx
  char *v57; // rbx
  char *v58; // rcx
  char v59; // cl
  BOOL v60; // eax
  char v61; // dl
  bool v62; // zf
  unsigned __int8 *v63; // rbx
  __int64 v64; // rcx
  char v66; // [rsp+70h] [rbp-2C8h]
  char v67[2]; // [rsp+72h] [rbp-2C6h] BYREF
  int v68; // [rsp+74h] [rbp-2C4h]
  char v69; // [rsp+78h] [rbp-2C0h]
  __int64 v70; // [rsp+80h] [rbp-2B8h]
  unsigned int v71; // [rsp+88h] [rbp-2B0h]
  PVOID P; // [rsp+90h] [rbp-2A8h]
  UNICODE_STRING Source; // [rsp+98h] [rbp-2A0h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-290h]
  __int16 v75; // [rsp+B0h] [rbp-288h]
  unsigned __int16 v76; // [rsp+B4h] [rbp-284h]
  USHORT v77; // [rsp+B8h] [rbp-280h]
  int v78; // [rsp+BCh] [rbp-27Ch]
  unsigned int v79; // [rsp+C0h] [rbp-278h]
  int v80; // [rsp+C4h] [rbp-274h]
  ULONG Seed; // [rsp+C8h] [rbp-270h] BYREF
  int v82; // [rsp+CCh] [rbp-26Ch]
  unsigned int v83; // [rsp+D0h] [rbp-268h]
  unsigned int v84; // [rsp+D4h] [rbp-264h]
  int v85; // [rsp+D8h] [rbp-260h]
  unsigned int v86; // [rsp+DCh] [rbp-25Ch]
  int v87; // [rsp+E0h] [rbp-258h]
  __int64 v88; // [rsp+E8h] [rbp-250h]
  PVOID v89; // [rsp+F0h] [rbp-248h]
  void *Src; // [rsp+F8h] [rbp-240h]
  struct _UNICODE_STRING Destination; // [rsp+100h] [rbp-238h] BYREF
  PVOID v92[2]; // [rsp+110h] [rbp-228h] BYREF
  int v93[4]; // [rsp+120h] [rbp-218h] BYREF
  __int64 v94; // [rsp+130h] [rbp-208h]
  __int64 v95; // [rsp+138h] [rbp-200h]
  PVOID Bcb[2]; // [rsp+140h] [rbp-1F8h] BYREF
  __int64 v97; // [rsp+150h] [rbp-1E8h]
  int v98; // [rsp+158h] [rbp-1E0h]
  char *v99; // [rsp+160h] [rbp-1D8h]
  __int64 v100; // [rsp+168h] [rbp-1D0h]
  __int64 v101; // [rsp+170h] [rbp-1C8h]
  __int64 v102; // [rsp+178h] [rbp-1C0h]
  ULONG v103; // [rsp+180h] [rbp-1B8h]
  PWSTR v104; // [rsp+188h] [rbp-1B0h]
  __int64 v105; // [rsp+190h] [rbp-1A8h]
  signed __int64 v106; // [rsp+198h] [rbp-1A0h] BYREF
  __int64 v107; // [rsp+1A0h] [rbp-198h]
  __int64 v108; // [rsp+1A8h] [rbp-190h]
  PVOID v109[2]; // [rsp+1B0h] [rbp-188h]
  __int64 v110[2]; // [rsp+1C0h] [rbp-178h] BYREF
  __int64 v111[12]; // [rsp+1D0h] [rbp-168h] BYREF
  __int64 v112[14]; // [rsp+230h] [rbp-108h] BYREF
  _QWORD v113[10]; // [rsp+2A0h] [rbp-98h] BYREF

  v105 = a4;
  v101 = a3;
  v102 = a1;
  v88 = a5;
  v107 = a7;
  Src = a8;
  v86 = 0;
  v10 = *(_QWORD *)(a3 + 96);
  v70 = v10;
  v108 = v10;
  v74 = *(_QWORD *)(v10 + 200);
  v68 = 0;
  Source = 0;
  Destination = 0;
  v67[0] = 0;
  P = 0;
  v71 = 0;
  v89 = 0;
  *(_OWORD *)v110 = 0;
  *(_OWORD *)v109 = 0;
  *(_OWORD *)v92 = 0;
  v87 = 0;
  v85 = 0;
  memset(v112, 0, sizeof(v112));
  memset(v113, 0, sizeof(v113));
  v100 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL);
  v94 = 0;
  *(_OWORD *)Bcb = 0;
  v97 = 0;
  v112[1] = (__int64)&v112[4];
  v112[3] = (__int64)&v112[7];
  LODWORD(v112[0]) = 1572864;
  LODWORD(v112[2]) = 3407872;
  v66 = 2;
  *(_WORD *)((char *)&Bcb[1] + 1) = 600;
  v11 = 88;
  *(_QWORD *)v93 = a1;
  v12 = a7;
  v95 = a7;
  v13 = v101;
  *(_QWORD *)&v93[2] = v101;
  if ( a5 )
  {
    v14 = *(_DWORD *)(a5 + 4);
    v68 = v14;
  }
  else
  {
    v14 = v68;
  }
  v109[1] = 0;
  v92[1] = 0;
  if ( (v14 & 8) == 0 )
    v11 = 89;
  v80 = v11;
  BYTE1(Bcb[1]) = v11;
  v15 = LOWORD(NtfsSystemFilesEx[2 * *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v10 + 200) + 184LL) + 34LL)]) + 50;
  v77 = v15;
  Destination.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v15, 0x3066744Eu);
  Source.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x30u, 0x3066744Eu);
  v16 = (char)Bcb[1];
  do
  {
    Seed = 0;
    v106 = 0;
    Destination.Length = 0;
    Destination.MaximumLength = v15;
    *(_DWORD *)&Source.Length = 3145776;
    RtlAppendUnicodeStringToString(
      &Destination,
      (PCUNICODE_STRING)&NtfsSystemFilesEx[2 * *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v70 + 200) + 184LL) + 34LL)]);
    RtlAppendUnicodeToString(&Destination, L"\\");
    v17 = *(unsigned int *)(v101 + 8)
        + ((*(unsigned __int16 *)(v101 + 12) + ((unsigned __int64)*(unsigned __int16 *)(v101 + 14) << 16)) << 32);
    v106 = v17;
    v78 = 0;
    Buffer = Source.Buffer;
    v19 = Source.Buffer + 16;
    v104 = Source.Buffer + 16;
    v20 = 0;
    i = 0;
    v79 = 0;
    while ( i < 0x10 )
    {
      if ( v20 )
        v22 = v17 >> 32;
      else
        LODWORD(v22) = v17;
      v78 = v22;
      for ( i = v20; ; ++i )
      {
        v79 = i;
        if ( i >= v20 + 8 )
          break;
        v104 = --v19;
        *v19 = HexTable[v22 & 0xF];
        LODWORD(v22) = (unsigned int)v22 >> 4;
        v78 = v22;
        Buffer = Source.Buffer;
      }
      v20 = i;
    }
    Seed = a6;
    v23 = RtlRandomEx(&Seed);
    v103 = v23;
    v82 = 0;
    for ( j = 7; ; --j )
    {
      v82 = j;
      if ( j < 0 )
        break;
      Buffer[j + 16] = HexTable[v23 & 0xF];
      v23 >>= 4;
      v103 = v23;
    }
    RtlAppendUnicodeStringToString(&Destination, &Source);
    if ( Source.Length > 0x1FEu )
      goto LABEL_124;
    v25 = 0;
    v83 = 0;
    v27 = 1;
    v69 = 1;
    v28 = 1;
    if ( !Source.Length || (Source.Length & 1) != 0 )
      goto LABEL_131;
    v29 = Source.Length >> 1;
    v30 = 0;
    v83 = 0;
    while ( v30 < v29 )
    {
      v75 = 0;
      v26 = Source.Buffer[v30];
      v75 = v26;
      if ( (unsigned __int16)v26 <= 0xFFu
        && (v26 & 0x80u) == 0LL
        && (v25 = 0, (*((_BYTE *)FsRtlLegalAnsiCharacterArray + v26) & 4) == 0)
        || (_DWORD)v26 == 58
        || (_WORD)v26 == 92 )
      {
        v28 = 0;
        break;
      }
      if ( (_DWORD)v26 != 46 )
        v27 = 0;
      v69 = v27;
      v83 = ++v30;
    }
    v14 = v68;
    if ( v27 )
    {
      if ( v29 - 1 <= 1 )
LABEL_131:
        v28 = 0;
    }
    if ( !v28 )
    {
LABEL_124:
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225523LL, 465481);
      v53 = -1073741773;
LABEL_127:
      v46 = P;
      goto LABEL_78;
    }
    v31 = (__int64)Src;
    if ( !*(_BYTE *)Src )
    {
      NtfsAcquireExclusiveScbEx(a1, v12, 0);
      *(_BYTE *)v31 = 1;
    }
    if ( !*(_WORD *)(v12 + 656) )
      NtfsBuildNormalizedNameWithTxfIsolation(a1, *(_QWORD *)(v12 + 184), v12, 0, 0, 0, v12 + 656);
    if ( !v105
      || *(_WORD *)v105 != 1795
      || *(_QWORD *)(v105 + 640) == v105 + 640
      || a1
      && ((*(_DWORD *)(a1 + 16) & 0x40000000) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 144) + 16LL) & 0x40000000) != 0)
      || ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a6 + 48) + 96LL) + 2160LL)) )
    {
      v31 = v74;
      if ( (*(_DWORD *)(a1 + 12) & 0x100) != 0 )
      {
        NtfsAcquireExclusiveScbEx(a1, v74, 0);
      }
      else
      {
        if ( !(unsigned __int8)NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(v74 + 184), v74, 2) )
        {
          *(_DWORD *)(a1 + 12) |= 0x100u;
          NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 465530);
LABEL_83:
          v99 = 0;
          v71 = 0;
          v55 = *(unsigned __int16 *)(a6 + 72) + 2 + *(unsigned __int16 *)(v12 + 656);
          v71 = v55;
          if ( v55 <= 0xFFFE )
          {
            PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v55, 0x3066744Eu);
            v92[1] = PoolWithTag;
            v99 = PoolWithTag;
            memmove(PoolWithTag, *(const void **)(v12 + 664), *(unsigned __int16 *)(v12 + 656));
            v57 = &PoolWithTag[*(unsigned __int16 *)(v12 + 656)];
            v99 = v57;
            if ( *(_WORD *)(v107 + 656) == 2 )
            {
              v55 -= 2;
              v71 = v55;
              v58 = v57;
            }
            else
            {
              *(_WORD *)v57 = 92;
              v58 = v57 + 2;
              LOWORD(v57) = (_WORD)v57 + 2;
              v99 = v58;
            }
            memmove(v58, *(const void **)(a6 + 80), *(unsigned __int16 *)(a6 + 72));
            LOWORD(v92[0]) = v55;
            WORD1(v92[0]) = v55;
            LOWORD(v87) = (_WORD)v57 - LOWORD(v92[1]);
            goto LABEL_57;
          }
          v53 = -1073741562;
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225734LL, 465657);
          goto LABEL_127;
        }
        if ( (*(_DWORD *)(v31 + 200) & 0x200) != 0 )
          NtfsSnapshotScb(a1, v31);
      }
      if ( (*(_BYTE *)(*(_QWORD *)(a6 + 192) + 65LL) & 3) != 0 && (v14 & 1) != 0 )
      {
        v66 |= 4u;
        BYTE2(Bcb[1]) = v66;
      }
      if ( (v14 & 1) == 0 )
      {
LABEL_42:
        v25 = 0;
        v98 = 0;
        goto LABEL_43;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 12) |= 0x100u;
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 465515);
    }
    if ( (v14 & 0x4000000) == 0 && (*(_DWORD *)(*(_QWORD *)(v31 + 184) + 16LL) & 0x400) != 0 )
      goto LABEL_42;
    v98 = 1;
    v25 = 0;
LABEL_43:
    v32 = Source.Length + 66;
    v84 = v32;
    if ( v32 <= (unsigned __int16)v71 )
    {
      v35 = P;
LABEL_50:
      v36 = v74;
      *(_QWORD *)v35 = *(_QWORD *)(*(_QWORD *)(v74 + 184) + 8LL);
      v35[32] = (unsigned __int8)(Source.Length >> 1);
      memmove(v35 + 33, Source.Buffer, Source.Length);
      IndexEntry = NtfsFindIndexEntry(a1, v36, (_DWORD)v35, 0, (__int64)Bcb, (__int64)&v106, 0);
      v66 = BYTE2(Bcb[1]);
      LOBYTE(v38) = BYTE1(Bcb[1]);
      v80 = v38;
      v16 = (char)Bcb[1];
      v13 = *(_QWORD *)&v93[2];
      v12 = v95;
      v25 = 0;
      goto LABEL_51;
    }
    if ( v32 <= 0xFFFF )
    {
      if ( P )
      {
        ExFreePoolWithTag(P, 0);
        P = 0;
        v76 = 0;
      }
      v33 = 0xFFFF;
      if ( 2 * v32 < 0xFFFF )
        v33 = 2 * v32;
      v34 = v33;
      v84 = v33;
      v35 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v33, 0x4146744Eu);
      P = v35;
      v71 = v34;
      v76 = v34;
      goto LABEL_50;
    }
    IndexEntry = 0;
LABEL_51:
    v16 = v16 & 0xDF | (32 * (IndexEntry & 1));
    LOBYTE(Bcb[1]) = v16;
    if ( *(_DWORD *)(a1 + 28) )
    {
      NtfsCheckpointCurrentTransaction(a1);
      NtfsReleaseSharedResources(a1);
      NtfsReleaseExclusiveScbIfOwned(a1, *(_QWORD *)(v70 + 48));
      v25 = 0;
    }
    v14 = v68;
    v15 = v77;
  }
  while ( (v16 & 0x20) != 0 );
  if ( (*(_BYTE *)(*(_QWORD *)(a6 + 192) + 65LL) & 3) == 2 )
  {
    memset(v111, 0, 0x58u);
    Src = 0;
    NtfsLookupPrimaryLink(a1, v13, (__int64)v111);
    v63 = (unsigned __int8 *)Src;
    v89 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 2LL * *((unsigned __int8 *)Src + 64) + 66, 0x3066744Eu);
    memmove(v89, v63, 2LL * v63[64] + 66);
    NtfsCleanupAttributeContext(v64, v111);
  }
  if ( (v80 & 1) != 0 )
    goto LABEL_83;
LABEL_57:
  if ( Bcb[0] )
  {
    CcUnpinData(Bcb[0]);
    Bcb[0] = 0;
  }
  LOBYTE(v113[9]) = 0;
  if ( *(int *)(v70 + 4) < 0 || (v40 = (_DWORD *)(v100 + 80), (*(_DWORD *)(v100 + 80) & 0x20000) != 0) )
  {
    v39 = 0;
    v40 = (_DWORD *)(v100 + 80);
  }
  else
  {
    v39 = v113;
  }
  NtfsRemoveLink(a1, v13, (__int64)v112, (__int64)v39);
  v41 = v70;
  if ( (v68 & 8) == 0 )
  {
    if ( (*(_DWORD *)(v13 + 176) & 0x10000000) == 0 )
    {
      if ( *(int *)(v70 + 4) >= 0 )
      {
        v40 = (_DWORD *)(v100 + 80);
        if ( (*(_DWORD *)(v100 + 80) & 0x20000) == 0 )
        {
          v59 = *(_BYTE *)(*(_QWORD *)(a6 + 192) + 65LL);
          v113[0] = *(_QWORD *)(v13 + 128);
          BYTE1(v113[9]) = (v59 & 2) != 0;
          v60 = (v68 & 0x4000000) == 0 && (*(_DWORD *)(*(_QWORD *)(v95 + 184) + 16LL) & 0x400) != 0;
          FsRtlAddToTunnelCacheEx(
            v70 + 4720,
            *(_QWORD *)(*(_QWORD *)(v95 + 184) + 8LL),
            v112,
            &v112[2],
            v60 | (2 * BYTE1(v113[9])),
            80,
            v113);
          v41 = v70;
        }
      }
      goto LABEL_62;
    }
    goto LABEL_63;
  }
LABEL_62:
  if ( (*(_DWORD *)(v13 + 176) & 0x10000000) != 0 || *(int *)(v41 + 4) < 0 )
  {
LABEL_63:
    v42 = v74;
    goto LABEL_64;
  }
  v62 = (*v40 & 0x20000) == 0;
  v42 = v74;
  if ( v62 )
  {
    v85 = 80;
    if ( (unsigned __int8)FsRtlFindInTunnelCacheEx(
                            v41 + 4720,
                            *(_QWORD *)(*(_QWORD *)(v74 + 184) + 8LL),
                            &Source,
                            v112,
                            &v112[2]) )
    {
      v16 |= 0x40u;
      LOBYTE(Bcb[1]) = v16;
      if ( (v16 & 1) == 0 )
      {
        if ( LOBYTE(v113[9]) )
        {
          NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v70 + 160), 0);
          v16 |= 1u;
          LOBYTE(Bcb[1]) = v16;
        }
      }
    }
  }
LABEL_64:
  v43 = (v16 & 0x40) != 0;
  NtfsAddLink(a1, v13, (__int64)P, 0, (__int64)v67, 0, 0, (unsigned __int64)v112 & -(__int64)v43, 0);
  if ( v43 )
  {
    NtfsSetTunneledData(a1, v13, v113, v44);
    *(_DWORD *)(v13 + 184) |= 0x40u;
    *(_DWORD *)(v13 + 4) |= 0x10u;
    if ( v67[0] == 2 )
      memmove(Source.Buffer, (const void *)v112[1], Source.Length);
  }
  v45 = v67[0];
  v46 = P;
  *((_BYTE *)P + 65) = v67[0];
  v47 = (__int64)v46;
  if ( (v45 & 3) == 2 )
    v47 = 0;
  NtfsMoveLinkToNewDir(a1, v42, v13, 0, a6, (char)Bcb[1], (__int64)v110, 10, (__int64)v89, v47);
  v48 = *(_QWORD *)(a6 + 192);
  LOBYTE(k) = *(_BYTE *)(v48 + 65) & 3;
  if ( (_BYTE)k == 1 || (v50 = 0, (_BYTE)k == 2) )
  {
    v61 = ((*(_BYTE *)(v48 + 65) & 3) == 1) + 1;
    v68 = ((*(_BYTE *)(v48 + 65) & 3) == 1) + 1;
    v50 = 0;
    for ( k = *(_QWORD **)(v101 + 48); k != (_QWORD *)(v101 + 48); k = (_QWORD *)*k )
    {
      if ( (*((_DWORD *)k - 13) & 2) == 0 && *(_BYTE *)(k[17] + 65LL) == v61 )
      {
        v50 = k - 7;
        break;
      }
    }
  }
  NtfsRemovePrefix(k, a6);
  if ( (*(_DWORD *)(a6 + 4) & 0x20) != 0 )
  {
    NtfsRemoveHashEntry(a1, *(_QWORD *)(*(_QWORD *)(a6 + 48) + 96LL) + 4968LL, *(unsigned int *)(a6 + 184), a6);
    *(_DWORD *)(a6 + 184) = 0;
    ClearFlagInterlocked(a6 + 4, 32);
  }
  *(_DWORD *)(a6 + 156) = 0;
  if ( v50 )
  {
    NtfsRemovePrefix(v51, v50);
    if ( (*((_DWORD *)v50 + 1) & 0x20) != 0 )
    {
      NtfsRemoveHashEntry(a1, *(_QWORD *)(v50[6] + 96LL) + 4968LL, *((unsigned int *)v50 + 46), v50);
      *((_DWORD *)v50 + 46) = 0;
      ClearFlagInterlocked((char *)v50 + 4, 32);
    }
    *((_DWORD *)v50 + 39) = 0;
  }
  if ( (*(_DWORD *)(a6 + 4) & 0x40) == 0 )
    _InterlockedOr((volatile signed __int32 *)(a6 + 4), 0x40u);
  if ( (*(_DWORD *)(v13 + 176) & 0x10000000) != 0 )
    NtfsUpdateNormalizedName(a1, 0);
  v52 = v95;
  NtfsUpdateFcbTimestamps(*(_QWORD *)(v95 + 184), 2684354576LL);
  if ( (v80 & 1) == 0 )
  {
    v53 = v86;
LABEL_78:
    v54 = v70;
    goto LABEL_140;
  }
  v54 = v70;
  NtfsReportDirNotify(
    a1,
    v52,
    v70,
    (unsigned int)v92,
    (unsigned __int16)v87,
    0,
    ((*(_DWORD *)(v13 + 176) & 0x10000000) != 0) + 1,
    2,
    *(_QWORD *)(v52 + 184),
    v13);
  v53 = v86;
LABEL_140:
  NtfsRenameCleanup(v93, v25, v26);
  if ( v89 )
    ExFreePoolWithTag(v89, 0);
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0);
  if ( Source.Buffer )
    ExFreePoolWithTag(Source.Buffer, 0);
  if ( v109[1] )
    ExFreePoolWithTag(v109[1], 0);
  if ( v92[1] )
    ExFreePoolWithTag(v92[1], 0);
  if ( v46 )
    ExFreePoolWithTag(v46, 0);
  if ( (__int64 *)v112[3] != &v112[7] )
    ExFreePoolWithTag((PVOID)v112[3], 0);
  if ( ((__int64)Bcb[1] & 1) != 0 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v54 + 160) + 184LL), 0);
  return v53;
}

```

## disassembly

```asm
0x1401493f4  push    rbx
0x1401493f6  push    rsi
0x1401493f7  push    rdi
0x1401493f8  push    r12
0x1401493fa  push    r13
0x1401493fc  push    r14
0x1401493fe  push    r15
0x140149400  sub     rsp, 300h
0x140149407  mov     rax, cs:__security_cookie
0x14014940e  xor     rax, rsp
0x140149411  mov     [rsp+338h+var_48], rax
0x140149419  mov     [rsp+338h+var_1A8], r9
0x140149421  mov     [rsp+338h+var_1C8], r8
0x140149429  mov     rbx, rdx
0x14014942c  mov     rdi, rcx
0x14014942f  mov     [rsp+338h+var_1C0], rcx
0x140149437  mov     rsi, [rsp+338h+arg_20]
0x14014943f  mov     [rsp+338h+var_250], rsi
0x140149447  mov     r15, [rsp+338h+arg_28]
0x14014944f  mov     r13, [rsp+338h+arg_30]
0x140149457  mov     [rsp+338h+var_198], r13
0x14014945f  mov     rax, [rsp+338h+arg_38]
0x140149467  mov     [rsp+338h+Src], rax
0x14014946f  xor     ecx, ecx
0x140149471  mov     [rsp+338h+var_25C], ecx
0x140149478  mov     r14, [r8+60h]
0x14014947c  mov     [rsp+338h+var_2B8], r14
0x140149484  mov     [rsp+338h+var_190], r14
0x14014948c  mov     rax, [r14+0C8h]
0x140149493  mov     [rsp+338h+var_290], rax
0x14014949b  mov     [rsp+338h+var_2C4], ecx
0x14014949f  xorps   xmm0, xmm0
0x1401494a2  movups  xmmword ptr [rsp+338h+Source.Length], xmm0
0x1401494aa  xorps   xmm1, xmm1
0x1401494ad  movups  xmmword ptr [rsp+338h+Destination.Length], xmm1
0x1401494b5  mov     [rsp+338h+var_2C6], cl
0x1401494b9  mov     [rsp+338h+P], rcx
0x1401494c1  mov     [rsp+338h+var_2B0], ecx
0x1401494c8  mov     [rsp+338h+var_248], rcx
0x1401494d0  movups  xmmword ptr [rsp+338h+var_178], xmm0
0x1401494d8  movups  xmmword ptr [rsp+338h+var_188], xmm1
0x1401494e0  movups  xmmword ptr [rsp+338h+var_228], xmm0
0x1401494e8  mov     [rsp+338h+var_258], ecx
0x1401494ef  mov     [rsp+338h+var_260], ecx
0x1401494f6  xor     edx, edx; Val
0x1401494f8  lea     r8d, [rcx+70h]; Size
0x1401494fc  lea     rcx, [rsp+338h+var_108]; void *
0x140149504  call    memset
0x140149509  xor     edx, edx; Val
0x14014950b  lea     r8d, [rdx+50h]; Size
0x14014950f  lea     rcx, [rsp+338h+var_98]; void *
0x140149517  call    memset
0x14014951c  mov     rax, [rbx+0B8h]
0x140149523  mov     rax, [rax+30h]
0x140149527  mov     [rsp+338h+var_1D0], rax
0x14014952f  xorps   xmm0, xmm0
0x140149532  xor     eax, eax
0x140149534  movups  xmmword ptr [rsp+338h+var_218], xmm0
0x14014953c  movups  [rsp+338h+var_208], xmm0
0x140149544  movups  xmmword ptr [rsp+338h+Bcb], xmm0
0x14014954c  mov     [rsp+338h+var_1E8], rax
0x140149554  lea     rax, [rsp+338h+var_E8]
0x14014955c  mov     [rsp+338h+var_100], rax
0x140149564  lea     rax, [rsp+338h+var_D0]
0x14014956c  mov     [rsp+338h+var_F0], rax
0x140149574  xor     edx, edx
0x140149576  mov     dword ptr [rsp+338h+var_108], 180000h
0x140149581  mov     [rsp+338h+var_F8], 340000h
0x14014958c  mov     cl, 2
0x14014958e  mov     [rsp+338h+var_2C8], cl
0x140149592  mov     word ptr [rsp+338h+Bcb+9], 258h
0x14014959c  lea     eax, [rdx+58h]
0x14014959f  mov     qword ptr [rsp+338h+var_218], rdi
0x1401495a7  mov     r12, r13
0x1401495aa  mov     qword ptr [rsp+338h+var_208+8], r13
0x1401495b2  mov     r9, [rsp+338h+var_1C8]
0x1401495ba  mov     r13, r9
0x1401495bd  mov     qword ptr [rsp+338h+var_218+8], r9
0x1401495c5  test    rsi, rsi
0x1401495c8  jz      loc_14014A7A4
0x1401495ce  mov     esi, [rsi+4]
0x1401495d1  mov     [rsp+338h+var_2C4], esi
0x1401495d5  mov     [rsp+338h+var_188+8], rdx
0x1401495dd  mov     [rsp+338h+var_228+8], rdx
0x1401495e5  test    sil, 8
0x1401495e9  mov     ecx, 59h ; 'Y'
0x1401495ee  cmovz   eax, ecx
0x1401495f1  mov     [rsp+338h+var_274], eax
0x1401495f8  mov     byte ptr [rsp+338h+Bcb+9], al
0x1401495ff  mov     rax, [r14+0C8h]
0x140149606  mov     rcx, [rax+0B8h]
0x14014960d  movzx   eax, word ptr [rcx+22h]
0x140149611  add     rax, rax
0x140149614  lea     rcx, NtfsSystemFilesEx
0x14014961b  movzx   ebx, word ptr [rcx+rax*8]
0x14014961f  add     bx, 32h ; '2'
0x140149623  mov     [rsp+338h+var_280], bx
0x14014962b  movzx   edx, bx; NumberOfBytes
0x14014962e  mov     ecx, cs:PoolType
0x140149634  or      ecx, 10h; PoolType
0x140149637  mov     r14d, 3066744Eh
0x14014963d  mov     r8d, r14d; Tag
0x140149640  call    cs:__imp_ExAllocatePoolWithTag
0x140149647  nop     dword ptr [rax+rax+00h]
0x14014964c  mov     [rsp+338h+Destination.Buffer], rax
0x140149654  mov     ecx, cs:PoolType
0x14014965a  or      ecx, 10h; PoolType
0x14014965d  mov     r8d, r14d; Tag
0x140149660  mov     edx, 30h ; '0'; NumberOfBytes
0x140149665  call    cs:__imp_ExAllocatePoolWithTag
0x14014966c  nop     dword ptr [rax+rax+00h]
0x140149671  mov     [rsp+338h+Source.Buffer], rax
0x140149679  mov     r14b, byte ptr [rsp+338h+Bcb+8]
0x140149681  xor     edx, edx
0x140149683  mov     [rsp+338h+Seed], edx
0x14014968a  mov     [rsp+338h+var_1A0], rdx
0x140149692  mov     [rsp+338h+Destination.Length], dx
0x14014969a  mov     [rsp+338h+Destination.MaximumLength], bx
0x1401496a2  mov     dword ptr [rsp+338h+Source.Length], 300030h
0x1401496ad  mov     rax, [rsp+338h+var_2B8]
0x1401496b5  mov     rax, [rax+0C8h]
0x1401496bc  mov     rcx, [rax+0B8h]
0x1401496c3  movzx   edx, word ptr [rcx+22h]
0x1401496c7  shl     rdx, 4
0x1401496cb  lea     rax, NtfsSystemFilesEx
0x1401496d2  add     rdx, rax; Source
0x1401496d5  lea     rcx, [rsp+338h+Destination]; Destination
0x1401496dd  call    cs:__imp_RtlAppendUnicodeStringToString
0x1401496e4  nop     dword ptr [rax+rax+00h]
0x1401496e9  lea     rdx, asc_140063E4C; "\\"
0x1401496f0  lea     rcx, [rsp+338h+Destination]; Destination
0x1401496f8  call    cs:__imp_RtlAppendUnicodeToString
0x1401496ff  nop     dword ptr [rax+rax+00h]
0x140149704  mov     rcx, [rsp+338h+var_1C8]
0x14014970c  movzx   r9d, word ptr [rcx+0Eh]
0x140149711  shl     r9, 10h
0x140149715  movzx   eax, word ptr [rcx+0Ch]
0x140149719  add     r9, rax
0x14014971c  shl     r9, 20h
0x140149720  mov     eax, [rcx+8]
0x140149723  add     r9, rax
0x140149726  mov     [rsp+338h+var_1A0], r9
0x14014972e  xor     eax, eax
0x140149730  mov     [rsp+338h+var_1B0], rax
0x140149738  mov     [rsp+338h+var_27C], eax
0x14014973f  mov     [rsp+338h+var_278], eax
0x140149746  mov     rbx, [rsp+338h+Source.Buffer]
0x14014974e  lea     r10, [rbx+20h]
0x140149752  mov     [rsp+338h+var_1B0], r10
0x14014975a  mov     r8d, eax
0x14014975d  mov     edx, eax
0x14014975f  mov     [rsp+338h+var_278], eax
0x140149766  lea     r11, HexTable; "0123456789ABCDEF"
0x14014976d  cmp     edx, 10h
0x140149770  jnb     short loc_1401497CF
0x140149772  test    r8d, r8d
0x140149775  jz      loc_140149F6F
0x14014977b  mov     rcx, r9
0x14014977e  sar     rcx, 20h
0x140149782  mov     [rsp+338h+var_27C], ecx
0x140149789  mov     edx, r8d
0x14014978c  mov     [rsp+338h+var_278], edx
0x140149793  lea     eax, [r8+8]
0x140149797  cmp     edx, eax
0x140149799  jnb     loc_140149F67
0x14014979f  sub     r10, 2
0x1401497a3  mov     [rsp+338h+var_1B0], r10
0x1401497ab  mov     eax, ecx
0x1401497ad  and     eax, 0Fh
0x1401497b0  movzx   eax, word ptr [r11+rax*2]
0x1401497b5  mov     [r10], ax
0x1401497b9  shr     ecx, 4
0x1401497bc  mov     [rsp+338h+var_27C], ecx
0x1401497c3  inc     edx
0x1401497c5  mov     rbx, [rsp+338h+Source.Buffer]
0x1401497cd  jmp     short loc_14014978C
0x1401497cf  mov     [rsp+338h+Seed], r15d
0x1401497d7  lea     rcx, [rsp+338h+Seed]; Seed
0x1401497df  call    cs:__imp_RtlRandomEx
0x1401497e6  nop     dword ptr [rax+rax+00h]
0x1401497eb  mov     [rsp+338h+var_1B8], eax
0x1401497f2  mov     [rsp+338h+var_26C], 0
0x1401497fd  mov     r8d, 7
0x140149803  lea     r9, HexTable; "0123456789ABCDEF"
0x14014980a  mov     [rsp+338h+var_26C], r8d
0x140149812  test    r8d, r8d
0x140149815  js      short loc_140149838
0x140149817  mov     ecx, eax
0x140149819  and     ecx, 0Fh
0x14014981c  movsxd  rdx, r8d
0x14014981f  movzx   ecx, word ptr [r9+rcx*2]
0x140149824  mov     [rbx+rdx*2+20h], cx
0x140149829  shr     eax, 4
0x14014982c  mov     [rsp+338h+var_1B8], eax
0x140149833  dec     r8d
0x140149836  jmp     short loc_14014980A
0x140149838  lea     rdx, [rsp+338h+Source]; Source
0x140149840  lea     rcx, [rsp+338h+Destination]; Destination
0x140149848  call    cs:__imp_RtlAppendUnicodeStringToString
0x14014984f  nop     dword ptr [rax+rax+00h]
0x140149854  mov     ecx, 1FEh
0x140149859  movzx   eax, [rsp+338h+Source.Length]
0x140149861  cmp     ax, cx
0x140149864  ja      loc_14014A444
0x14014986a  xor     edx, edx
0x14014986c  mov     [rsp+338h+var_268], edx
0x140149873  mov     r11b, 1
0x140149876  mov     [rsp+338h+var_2C0], r11b
0x14014987b  mov     r9b, r11b
0x14014987e  mov     [rsp+338h+var_2C7], r11b
0x140149883  test    ax, ax
0x140149886  jz      loc_14014A48F
0x14014988c  test    r11b, al
0x14014988f  jnz     loc_14014A48F
0x140149895  mov     ebx, eax
0x140149897  shr     ebx, 1
0x140149899  mov     r10d, edx
0x14014989c  mov     [rsp+338h+var_268], edx
0x1401498a3  mov     rsi, [rsp+338h+Source.Buffer]
0x1401498ab  cmp     r10d, ebx
0x1401498ae  jnb     short loc_140149922
0x1401498b0  mov     [rsp+338h+var_288], dx
0x1401498b8  mov     eax, r10d
0x1401498bb  movzx   r8d, word ptr [rsi+rax*2]
0x1401498c0  mov     [rsp+338h+var_288], r8w
0x1401498c9  mov     eax, 0FFh
0x1401498ce  cmp     r8w, ax
0x1401498d2  ja      short loc_1401498EC
0x1401498d4  test    r8b, r8b
0x1401498d7  js      short loc_1401498EC
0x1401498d9  mov     rax, cs:FsRtlLegalAnsiCharacterArray
0x1401498e0  mov     rcx, [rax]
0x1401498e3  xor     edx, edx
0x1401498e5  test    byte ptr [r8+rcx], 4
0x1401498ea  jz      short loc_14014991B
0x1401498ec  cmp     r8d, 3Ah ; ':'
0x1401498f0  jz      short loc_14014991B
0x1401498f2  mov     eax, 5Ch ; '\'
0x1401498f7  cmp     r8w, ax
0x1401498fb  jz      short loc_14014991B
0x1401498fd  movzx   r11d, r11b
0x140149901  cmp     r8d, 2Eh ; '.'
0x140149905  cmovnz  r11d, edx
0x140149909  mov     [rsp+338h+var_2C0], r11b
0x14014990e  inc     r10d
0x140149911  mov     [rsp+338h+var_268], r10d
0x140149919  jmp     short loc_1401498AB
0x14014991b  mov     r9b, dl
0x14014991e  mov     [rsp+338h+var_2C7], dl
0x140149922  mov     esi, [rsp+338h+var_2C4]
0x140149926  test    r11b, r11b
0x140149929  jnz     loc_14014A483
0x14014992f  test    r9b, r9b
0x140149932  jz      loc_14014A444
0x140149938  mov     rbx, [rsp+338h+Src]
0x140149940  cmp     [rbx], dl
0x140149942  jnz     short loc_140149957
0x140149944  xor     r8d, r8d
0x140149947  mov     rdx, r12
0x14014994a  mov     rcx, rdi
0x14014994d  call    NtfsAcquireExclusiveScbEx
0x140149952  mov     byte ptr [rbx], 1
0x140149955  xor     edx, edx
0x140149957  lea     rax, [r12+290h]
0x14014995f  cmp     [rax], dx
0x140149962  jnz     short loc_140149989
0x140149964  mov     qword ptr [rsp+338h+var_308], rax
0x140149969  mov     [rsp+338h+var_310], rdx
0x14014996e  mov     qword ptr [rsp+338h+var_318], rdx
0x140149973  xor     r9d, r9d
0x140149976  mov     r8, r12
0x140149979  mov     rdx, [r12+0B8h]
0x140149981  mov     rcx, rdi
0x140149984  call    NtfsBuildNormalizedNameWithTxfIsolation
0x140149989  mov     rax, [rsp+338h+var_1A8]
0x140149991  test    rax, rax
0x140149994  jnz     loc_14014A0B1
0x14014999a  mov     rbx, [rsp+338h+var_290]
0x1401499a2  mov     rcx, rdi
0x1401499a5  test    dword ptr [rdi+0Ch], 100h
0x1401499ac  jz      loc_140149F77
0x1401499b2  xor     r8d, r8d
0x1401499b5  mov     rdx, rbx
0x1401499b8  call    NtfsAcquireExclusiveScbEx
0x1401499bd  mov     rax, [r15+0C0h]
0x1401499c4  test    byte ptr [rax+41h], 3
0x1401499c8  setnz   cl
0x1401499cb  test    sil, 1
0x1401499cf  setnz   al
0x1401499d2  test    al, cl
0x1401499d4  jnz     loc_14014A16D
0x1401499da  test    sil, 1
0x1401499de  jnz     loc_14014A140
0x1401499e4  xor     edx, edx
0x1401499e6  mov     esi, edx
0x1401499e8  mov     [rsp+338h+var_1E0], edx
0x1401499ef  mov     [rsp+338h+var_264], edx
0x1401499f6  movzx   ebx, [rsp+338h+Source.Length]
0x1401499fe  add     ebx, 42h ; 'B'
0x140149a01  mov     [rsp+338h+var_264], ebx
  ... truncated ...
```
