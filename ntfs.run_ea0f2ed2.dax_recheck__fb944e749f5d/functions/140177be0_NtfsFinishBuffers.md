# NtfsFinishBuffers

- ea: `0x140177be0`
- end: `0x140179027`
- name: `NtfsFinishBuffers`
- size: `5191`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x140175a80`

## callees

- `0x140005f40`
- `0x140007ea0`
- `0x14000c290`
- `0x140012e70`
- `0x1400258cc`
- `0x140028930`
- `0x14003094c`
- `0x140038080`
- `0x14003b0d4`
- `0x14003bb28`
- `0x140046364`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x140140380`
- `0x140160e90`
- `0x14017517c`
- `0x140175220`
- `0x140177be0`
- `0x1401c0b50`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x1401781e2`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140178594`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x1401781e2`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140178594`
- `ntoskrnl!MmMdlPageContentsState` at `0x140177f84`
- `ntoskrnl!MmMdlPageContentsState` at `0x14017805f`
- `ntoskrnl!MmMdlPageContentsState` at `0x140178611`
- `ntoskrnl!MmMdlPageContentsState` at `0x140177f84`
- `ntoskrnl!MmMdlPageContentsState` at `0x14017805f`
- `ntoskrnl!MmMdlPageContentsState` at `0x140178611`
- `ntoskrnl!RtlDecompressFragmentEx` at `0x1401780d8`
- `ntoskrnl!RtlDecompressFragmentEx` at `0x140178790`
- `ntoskrnl!RtlDecompressFragmentEx` at `0x1401780d8`
- `ntoskrnl!RtlDecompressFragmentEx` at `0x140178790`
- `ntoskrnl!RtlDecompressBufferEx2` at `0x140177ff1`
- `ntoskrnl!RtlDecompressBufferEx2` at `0x140177ff1`
- `ntoskrnl!KeFlushIoBuffers` at `0x140178a68`
- `ntoskrnl!KeFlushIoBuffers` at `0x140178a82`
- `ntoskrnl!KeFlushIoBuffers` at `0x140178a68`
- `ntoskrnl!KeFlushIoBuffers` at `0x140178a82`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140178985`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140178985`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140178fb6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402a9f8c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140178fb6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402a9f8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140178cdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a9f6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140178cdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a9f6b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140178219`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401782b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401785cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14017863d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140178672`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14017886f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140178894`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401788c1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140178219`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401782b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401785cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14017863d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140178672`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14017886f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140178894`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401788c1`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140178239`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401785e7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140178239`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401785e7`

## pseudocode

```c
__int64 __fastcall NtfsFinishBuffers(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  __int64 v9; // r11
  __int64 v11; // rbx
  unsigned int v12; // r12d
  __int64 v13; // r14
  char v14; // r14
  __int64 v15; // r9
  _QWORD *v16; // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // r8
  ULONG v21; // eax
  int v22; // ecx
  __int64 v23; // rdx
  unsigned int v24; // r12d
  __int64 v25; // r8
  __int64 v26; // r14
  __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // r8d
  __int64 v30; // rdx
  ULONG v31; // r13d
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // r12
  __int64 v35; // rcx
  char v36; // al
  __int64 v37; // r10
  ULONG v38; // r8d
  ULONG v39; // edx
  PVOID PoolWithTag; // rax
  int v41; // eax
  int v42; // ecx
  int v43; // ecx
  unsigned int v44; // r12d
  _DWORD *v45; // rdx
  int v46; // eax
  int v47; // ecx
  size_t v48; // r8
  NTSTATUS CompressionWorkSpaceSize; // eax
  NTSTATUS v50; // edx
  PVOID v51; // rax
  PVOID v52; // rax
  NTSTATUS v53; // edx
  __int64 v54; // r8
  __int64 v55; // rax
  unsigned int v56; // edx
  int v57; // r8d
  int v58; // eax
  NTSTATUS v59; // eax
  PVOID v60; // rax
  unsigned int v61; // eax
  unsigned int v62; // eax
  int v63; // eax
  void *v64; // rcx
  __int64 v65; // r8
  PVOID v66; // rdx
  int v67; // eax
  size_t v68; // r8
  __int64 v70; // rdx
  __int64 v71; // rax
  char v72; // cl
  int v73; // r8d
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rax
  _QWORD *v78; // rcx
  char v79[8]; // [rsp+20h] [rbp-1E8h]
  char v80[8]; // [rsp+20h] [rbp-1E8h]
  __int64 v81; // [rsp+30h] [rbp-1D8h]
  char v82; // [rsp+50h] [rbp-1B8h]
  char v83; // [rsp+51h] [rbp-1B7h]
  int v84; // [rsp+54h] [rbp-1B4h]
  char v85; // [rsp+58h] [rbp-1B0h]
  unsigned int NumberOfBytes; // [rsp+5Ch] [rbp-1ACh]
  unsigned int NumberOfBytes_4; // [rsp+60h] [rbp-1A8h]
  NTSTATUS v88; // [rsp+64h] [rbp-1A4h]
  unsigned int v89; // [rsp+68h] [rbp-1A0h]
  PVOID P; // [rsp+70h] [rbp-198h]
  ULONG v91; // [rsp+78h] [rbp-190h]
  unsigned int v92; // [rsp+7Ch] [rbp-18Ch]
  _DWORD *Src; // [rsp+80h] [rbp-188h]
  size_t Size; // [rsp+88h] [rbp-180h] BYREF
  __int64 v95; // [rsp+90h] [rbp-178h]
  __int64 v96; // [rsp+98h] [rbp-170h]
  unsigned int v97; // [rsp+A0h] [rbp-168h]
  ULONG v98; // [rsp+A4h] [rbp-164h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+A8h] [rbp-160h] BYREF
  __int64 v100; // [rsp+B0h] [rbp-158h] BYREF
  size_t v101; // [rsp+B8h] [rbp-150h] BYREF
  __int64 v102; // [rsp+C0h] [rbp-148h]
  __int64 v103; // [rsp+C8h] [rbp-140h]
  _WORD *v104; // [rsp+D0h] [rbp-138h]
  __int64 v105; // [rsp+D8h] [rbp-130h] BYREF
  ULONG v106; // [rsp+E0h] [rbp-128h] BYREF
  ULONG CompressBufferWorkSpaceSize[3]; // [rsp+E4h] [rbp-124h] BYREF
  __int64 v108; // [rsp+F0h] [rbp-118h]
  _BYTE *v109; // [rsp+F8h] [rbp-110h]
  __int64 v110; // [rsp+100h] [rbp-108h]
  __int64 v111; // [rsp+108h] [rbp-100h]
  __int64 v112; // [rsp+110h] [rbp-F8h]
  __int64 v113; // [rsp+118h] [rbp-F0h]
  __int64 v114; // [rsp+120h] [rbp-E8h]
  __int64 v115; // [rsp+128h] [rbp-E0h]
  void *v116; // [rsp+130h] [rbp-D8h]
  __int64 v117; // [rsp+138h] [rbp-D0h]
  __int64 v118; // [rsp+140h] [rbp-C8h]
  __int64 v119; // [rsp+148h] [rbp-C0h]
  __int64 v120; // [rsp+150h] [rbp-B8h]
  __int64 v121; // [rsp+158h] [rbp-B0h]
  __int64 v122; // [rsp+160h] [rbp-A8h]
  __int64 v123; // [rsp+168h] [rbp-A0h]
  _QWORD *v124; // [rsp+170h] [rbp-98h]
  _QWORD v125[8]; // [rsp+180h] [rbp-88h] BYREF

  v9 = a2;
  v95 = a2;
  v119 = a1;
  v120 = a2;
  v121 = a3;
  v114 = a7;
  v11 = 0;
  v103 = 0;
  v105 = 0;
  Size = 0;
  v100 = 0;
  v12 = 0;
  v13 = *(_QWORD *)(a3 + 192);
  v111 = v13;
  v118 = v13;
  if ( *(_BYTE *)(a1 + 32) != 3 )
  {
    if ( !*(_BYTE *)(a7 + 105) )
      goto LABEL_3;
    v71 = *(_QWORD *)(a1 + 192);
    if ( !v71 || *(_QWORD *)(v71 + 80) != a3 )
      goto LABEL_3;
    v72 = 0;
    v73 = *(_DWORD *)(a3 + 452);
    v74 = -v73;
    v75 = a4 & v74;
    v76 = a5 + a4;
    v102 = v76;
    if ( v76 < *(_QWORD *)(a7 + 24) )
    {
      v77 = v74 & v76;
      v102 = v77;
      if ( v77 <= v75 )
        goto LABEL_179;
      v12 = NtfsPersistDelayedAllocation(a1, v75 >> *(_BYTE *)(v13 + 488), (v77 >> *(_BYTE *)(v13 + 488)) - 1, 0);
      if ( (v12 & 0x80000000) != 0 )
      {
        if ( NtfsStatusDebugFlags
          && v12 < 0xFFFFFFED
          && v12 != -1073741802
          && v12 != -1073741807
          && v12 + 2147483643 > 1
          && v12 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v12, 794965);
        }
        NtfsRaiseStatusInternal(a1, v12, 0, 0, 794965);
        __debugbreak();
      }
      if ( *(_DWORD *)(a1 + 28) )
      {
        if ( *(_BYTE *)(a3 + 460) )
        {
          if ( (*(_DWORD *)(v13 + 24) & 0x8000000) != 0 && !(unsigned __int8)NtfsReserveClusters(a1, 1) )
          {
            NtfsAllocateDiskFullContext(a1, a5, 0x274000C216ELL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3221225599LL, 794991);
            NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 794991);
            __debugbreak();
          }
          v11 = v102;
        }
        v72 = 1;
        goto LABEL_178;
      }
    }
    else
    {
      v12 = NtfsPersistDelayedAllocation(
              a1,
              v75 >> *(_BYTE *)(v13 + 488),
              ((v74 & (a5 + a4 + v73 - 1)) >> *(_BYTE *)(v13 + 488)) - 1,
              0);
      if ( (v12 & 0x80000000) != 0 )
      {
        if ( NtfsStatusDebugFlags
          && v12 < 0xFFFFFFED
          && v12 != -1073741802
          && v12 != -1073741807
          && v12 + 2147483643 > 1
          && v12 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v12, 794907);
        }
        NtfsRaiseStatusInternal(a1, v12, 0, 0, 794907);
        __debugbreak();
      }
      if ( *(_DWORD *)(a1 + 28) && *(_BYTE *)(a3 + 460) )
      {
        if ( (*(_DWORD *)(v13 + 24) & 0x8000000) != 0 && !(unsigned __int8)NtfsReserveClusters(a1, 1) )
        {
          NtfsAllocateDiskFullContext(a1, a5, 0x273000C2137LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225599LL, 794936);
          NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 794936);
          __debugbreak();
        }
        v11 = v102;
      }
    }
    v72 = 0;
LABEL_178:
    v9 = v95;
LABEL_179:
    if ( v11 > *(_QWORD *)(a3 + 464) )
      *(_QWORD *)(a3 + 464) = v11;
    if ( v72 )
    {
      NtfsCheckpointCurrentTransaction(a1);
      v9 = v95;
    }
LABEL_3:
    if ( v9 == *(_QWORD *)(a1 + 112) && !*(_DWORD *)(a7 + 68) )
    {
      if ( *(_BYTE *)(a7 + 107) )
      {
        v14 = 0;
        NtfsCheckpointCurrentTransaction(a1);
        *(_DWORD *)(a1 + 4) &= ~0x2000u;
        v16 = (_QWORD *)(a1 + 152);
        while ( 1 )
        {
          v17 = (_QWORD *)*v16;
          if ( (_QWORD *)*v16 == v16 )
            break;
          v18 = *(_QWORD **)(a3 + 184);
          if ( v17 - 10 == v18 )
          {
            v19 = v18[10];
            if ( *(_QWORD **)(v19 + 8) != v18 + 10 )
              goto LABEL_157;
            v20 = (_QWORD *)v18[11];
            if ( (_QWORD *)*v20 != v18 + 10 )
              goto LABEL_157;
            *v20 = v19;
            *(_QWORD *)(v19 + 8) = v20;
            v14 = 1;
          }
          else
          {
            NtfsReleaseFcbEx(a1, v17 - 10, 0);
          }
        }
        if ( v14 )
        {
          if ( (_QWORD *)v17[1] != v16 )
LABEL_157:
            __fastfail(3u);
          v78 = (_QWORD *)(*(_QWORD *)(a3 + 184) + 80LL);
          *v78 = v17;
          v78[1] = v16;
          v17[1] = v78;
          *v16 = v78;
          LOBYTE(v15) = 1;
          NtfsDeallocateCompressionBuffer(a1, v95, a7, v15);
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          *(_BYTE *)(a7 + 107) = 0;
        }
      }
      *(_BYTE *)(a7 + 109) = 0;
    }
    return v12;
  }
  if ( *(_QWORD *)(a3 + 504) && *(int *)(a3 + 200) >= 0 && *(_DWORD *)(a3 + 256) == 128 && (_QWORD)xmmword_140095740 )
  {
    NtfsDecryptBuffers(a1, a2, a3, a4, a6, a7);
    v9 = v95;
  }
  v104 = (_WORD *)(a3 + 460);
  if ( !*(_BYTE *)(a3 + 460) )
    return 0;
  if ( *(_DWORD *)(a7 + 68) )
    goto LABEL_153;
  v115 = a7;
  v122 = a3 + 460;
  v83 = 0;
  P = 0;
  v21 = *(_DWORD *)(a3 + 452);
  v98 = v21;
  CompressBufferWorkSpaceSize[2] = v21;
  v109 = (_BYTE *)(v13 + 488);
  v22 = *(_DWORD *)(v13 + 488);
  v23 = *(unsigned int *)(v13 + 480);
  v24 = ((unsigned int)v23 + v21) >> v22;
  v92 = 0;
  NumberOfBytes_4 = 0;
  v84 = 0;
  v124 = (_QWORD *)(a7 + 48);
  v25 = *(_QWORD *)(a7 + 48);
  v96 = v25;
  if ( !v25 )
  {
    v25 = *(_QWORD *)(v9 + 8);
    v96 = v25;
  }
  v112 = v25;
  CompressFragmentWorkSpaceSize = v21 - 1;
  v97 = (v21 - 1) & a4;
  v26 = (a4 + v23 - v97) >> v22;
  v113 = v26;
  if ( (unsigned __int8)NtfsLookupAllocation(a1, (__int64)&v100) )
  {
    v27 = v103;
  }
  else
  {
    v27 = -1;
    v103 = -1;
  }
  v28 = v100;
  if ( v100 >= 0x7FFFFFFFFFFFFFFFLL - v26 )
  {
    v85 = 0;
    goto LABEL_161;
  }
  v85 = 1;
  if ( v27 == -1 )
  {
LABEL_161:
    v28 = 0;
    v100 = 0;
  }
  v102 = v28 + v26;
  v105 = 0;
  v29 = a5;
  v30 = a5 + a4 + (int)CompressFragmentWorkSpaceSize;
  v31 = v98;
  v32 = (__int64)(-v98 & (unsigned __int64)v30) >> *v109;
  v110 = v32;
  v108 = v24;
  while ( v29 )
  {
    v33 = NtfsMapCompressionContext(a7, v95);
    v34 = v33;
    if ( v33 )
      v34 = *(unsigned int *)(a7 + 64) + v33;
    v35 = v105;
    v36 = v85;
    v37 = v102;
LABEL_26:
    while ( v36 && v100 < v108 && v100 + v26 == v37 )
    {
      v100 += v35;
      while ( 1 )
      {
        v37 += v35;
        v102 = v37;
        if ( v37 >= v110 )
        {
          v36 = 1;
          v85 = 1;
          goto LABEL_26;
        }
        if ( (unsigned __int8)NtfsLookupAllocation(a1, (__int64)&v105) )
        {
          v70 = v103;
        }
        else
        {
          v70 = -1;
          v103 = -1;
        }
        v37 = v102;
        v35 = v105;
        if ( v105 >= 0x7FFFFFFFFFFFFFFFLL - v102 )
          break;
        v36 = 1;
        v85 = 1;
        if ( v70 != -1 )
          goto LABEL_26;
      }
      v36 = 0;
      v85 = 0;
    }
    v123 = v108;
    if ( v100 < v108 )
    {
      v38 = (_DWORD)v100 << *(_DWORD *)v109;
      v91 = v38;
      v100 = 0;
    }
    else
    {
      v38 = v31;
      v91 = v31;
      v100 -= v108;
    }
    v39 = a5;
    if ( v31 - v97 <= a5 )
      v39 = v31 - v97;
    NumberOfBytes = v39;
    CompressBufferWorkSpaceSize[1] = v39;
    if ( v38 )
    {
      if ( v38 == v31 )
      {
        NtfsCopyIntoMdl(a1, v96, v39, *(_DWORD *)(a7 + 64) + NumberOfBytes_4, *(_QWORD *)(a7 + 32) + v92 + v97);
        v43 = v84;
        v44 = NumberOfBytes;
      }
      else
      {
        if ( v34 )
        {
          v82 = 0;
          if ( v39 >= v31 )
          {
            if ( (unsigned int)MmMdlPageContentsState(v96, 2) == 1 )
            {
              PoolWithTag = (PVOID)(v34 + NumberOfBytes_4);
            }
            else
            {
              PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, NumberOfBytes, 0x4446744Eu);
              P = PoolWithTag;
              if ( !PoolWithTag )
              {
                PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), NumberOfBytes, 0x4446744Eu);
                P = PoolWithTag;
              }
            }
            Src = PoolWithTag;
            goto LABEL_39;
          }
          if ( *(_QWORD *)(a7 + 96) )
          {
LABEL_44:
            if ( (unsigned int)MmMdlPageContentsState(v96, 2) == 1 )
            {
              v45 = (_DWORD *)(v34 + NumberOfBytes_4);
              Src = v45;
            }
            else
            {
              v52 = ExAllocatePoolWithTag((POOL_TYPE)512, NumberOfBytes, 0x4446744Eu);
              P = v52;
              if ( !v52 )
              {
                v52 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), NumberOfBytes, 0x4446744Eu);
                P = v52;
              }
              v45 = v52;
              Src = v52;
            }
            while ( 1 )
            {
              LODWORD(v81) = 4096;
              *(_DWORD *)v79 = v91;
              v46 = RtlDecompressFragmentEx(
                      (unsigned __int16)((unsigned __int8)*v104 + 1),
                      v45,
                      NumberOfBytes,
                      *(_QWORD *)(a7 + 32) + v92,
                      *(_QWORD *)v79,
                      v97,
                      v81,
                      &Size,
                      *(_QWORD *)(a7 + 96));
              v47 = v46;
              v84 = v46;
              if ( P && (v46 >= 0 || v82) )
              {
                v48 = NumberOfBytes;
                if ( v46 >= 0 )
                  v48 = (unsigned int)Size;
                memmove((void *)(v34 + NumberOfBytes_4), Src, v48);
                v47 = v84;
              }
              if ( v47 >= 0 )
                break;
              if ( NtfsStatusDebugFlags
                && (unsigned int)v47 < 0xFFFFFFED
                && v47 != -1073741802
                && v47 != -1073741807
                && (unsigned int)(v47 + 2147483643) > 1
                && v47 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(0, (unsigned int)v47, 794621);
              }
              v43 = 0;
              v84 = 0;
              if ( v82 )
                goto LABEL_42;
              memset(Src, 223, NumberOfBytes);
              v82 = 1;
              v45 = Src;
            }
LABEL_41:
            memset((void *)(v34 + NumberOfBytes_4 + (unsigned int)Size), 0, NumberOfBytes - (unsigned int)Size);
            v43 = v84;
          }
          else
          {
            CompressBufferWorkSpaceSize[0] = 0;
            CompressFragmentWorkSpaceSize = 0;
            CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                         (unsigned __int8)*v104 + 1,
                                         CompressBufferWorkSpaceSize,
                                         &CompressFragmentWorkSpaceSize);
            v50 = CompressionWorkSpaceSize;
            v88 = CompressionWorkSpaceSize;
            if ( CompressionWorkSpaceSize >= 0 )
            {
              if ( CompressFragmentWorkSpaceSize )
              {
                v51 = ExAllocatePoolWithTag(PoolType, CompressFragmentWorkSpaceSize, 0x4446744Eu);
                *(_QWORD *)(a7 + 96) = v51;
                if ( !v51 )
                {
                  KeAcquireGuardedMutex(&stru_140095940);
                  v83 = 1;
                  *(_QWORD *)(a7 + 96) = qword_1400959A8;
                }
              }
              goto LABEL_44;
            }
            if ( NtfsStatusDebugFlags
              && (unsigned int)CompressionWorkSpaceSize < 0xFFFFFFED
              && CompressionWorkSpaceSize != -1073741802
              && CompressionWorkSpaceSize != -1073741807
              && (unsigned int)(CompressionWorkSpaceSize + 2147483643) > 1
              && CompressionWorkSpaceSize != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(a1, (unsigned int)CompressionWorkSpaceSize, 794512);
              v50 = v88;
            }
            NtfsRaiseStatusInternal(a1, v50, 0, 0, 794512);
            while ( 1 )
            {
              if ( NtfsStatusDebugFlags
                && (unsigned int)v42 < 0xFFFFFFED
                && v42 != -1073741802
                && v42 != -1073741807
                && (unsigned int)(v42 + 2147483643) > 1
                && v42 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(0, (unsigned int)v42, 794760);
              }
              v43 = 0;
              v84 = 0;
              if ( v82 )
                break;
              memset(Src, 219, NumberOfBytes);
              v82 = 1;
              PoolWithTag = Src;
LABEL_39:
              *(_DWORD *)v79 = v91;
              v41 = RtlDecompressBufferEx2(
                      (unsigned __int16)((unsigned __int8)*v104 + 1),
                      PoolWithTag,
                      NumberOfBytes,
                      *(_QWORD *)(a7 + 32) + v92,
                      *(_QWORD *)v79,
                      4096,
                      &Size,
                      0);
              v42 = v41;
              v84 = v41;
              if ( P && (v41 >= 0 || v82) )
              {
                v68 = NumberOfBytes;
                if ( v41 >= 0 )
                  v68 = (unsigned int)Size;
                memmove((void *)(v34 + NumberOfBytes_4), Src, v68);
                v42 = v84;
              }
              if ( v42 >= 0 )
                goto LABEL_41;
            }
          }
LABEL_42:
          v44 = NumberOfBytes;
          goto LABEL_147;
        }
        memset(v125, 0, sizeof(v125));
        v44 = NumberOfBytes;
        v89 = NumberOfBytes;
        LODWORD(v101) = 0;
        Size = 0;
        v125[0] = 0;
        LODWORD(v125[1]) = 64;
        v125[4] = 0;
        v125[5] = 0x2000;
        if ( *(_QWORD *)(a7 + 96) )
          goto LABEL_117;
        v106 = 0;
        v98 = 0;
        v59 = RtlGetCompressionWorkSpaceSize((unsigned __int8)*v104 + 1, &v106, &v98);
        v53 = v59;
        v84 = v59;
        if ( v59 >= 0 )
        {
          if ( v98 )
          {
            v60 = ExAllocatePoolWithTag(PoolType, v98, 0x4446744Eu);
            *(_QWORD *)(a7 + 96) = v60;
            if ( !v60 )
            {
              KeAcquireGuardedMutex(&stru_140095940);
              v83 = 1;
              *(_QWORD *)(a7 + 96) = qword_1400959A8;
            }
          }
LABEL_117:
          if ( (unsigned int)MmMdlPageContentsState(v96, 2) != 1 )
          {
            v61 = 4096;
            if ( NumberOfBytes < 0x1000 )
              v61 = NumberOfBytes;
            P = ExAllocatePoolWithTag((POOL_TYPE)512, v61, 0x4446744Eu);
            if ( !P )
            {
              v62 = 4096;
              if ( NumberOfBytes < 0x1000 )
                v62 = NumberOfBytes;
              P = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v62, 0x4446744Eu);
            }
          }
          Src = (_DWORD *)(v115 + 64);
          v57 = Size;
          v43 = v84;
          v32 = NumberOfBytes;
          goto LABEL_125;
        }
        if ( NtfsStatusDebugFlags
          && (unsigned int)v59 < 0xFFFFFFED
          && v59 != -1073741802
          && v59 != -1073741807
          && (unsigned int)(v59 + 2147483643) > 1
          && v59 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v59, 794335);
          v53 = v84;
        }
        NtfsRaiseStatusInternal(a1, v53, 0, 0, 794335);
LABEL_80:
        if ( NtfsStatusDebugFlags
          && (unsigned int)v43 < 0xFFFFFFED
          && v43 != -1073741802
          && v43 != -1073741807
          && (unsigned int)(v43 + 2147483643) > 1
          && v43 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(0, (unsigned int)v43, 794433);
        }
        v84 = 0;
        v54 = 4096;
        if ( v89 < 0x1000 )
          v54 = v89;
        v79[0] = -33;
        NtfsFillMdl(a1, v96, v54, *Src + v44 + NumberOfBytes, *(_DWORD *)v79);
        v55 = 4096;
        v56 = v89;
        if ( v89 < 0x1000 )
          v55 = v89;
        v57 = v55 + Size;
        Size += v55;
        v43 = 0;
        while ( 1 )
        {
          v58 = v56;
          if ( v56 > 0x1000 )
            v58 = 4096;
          v32 = v56 - v58;
          v89 = v32;
LABEL_125:
          if ( !(_DWORD)v32 )
            break;
          v63 = 4096;
          if ( (unsigned int)v32 < 0x1000 )
            v63 = v32;
          NumberOfBytes = NumberOfBytes_4 - v32;
          v117 = v111 + 5384;
          Src = (_DWORD *)(a7 + 64);
          v64 = (void *)NtfsReservedMapBuffer(
                          v111 + 5384,
                          v96,
                          v125,
                          *(_DWORD *)(a7 + 64) + NumberOfBytes_4 - (_DWORD)v32 + v44,
                          v63);
          v116 = v64;
          v65 = 4096;
          if ( v89 < 0x1000 )
            v65 = v89;
          v66 = P;
          if ( !P )
            v66 = v64;
          LODWORD(v81) = 4096;
          *(_DWORD *)v80 = v91;
          v67 = RtlDecompressFragmentEx(
                  (unsigned __int16)((unsigned __int8)*v104 + 1),
                  v66,
                  v65,
                  *(_QWORD *)(a7 + 32) + v92,
                  *(_QWORD *)v80,
                  v97 + v44 - v89,
                  v81,
                  &v101,
                  *(_QWORD *)(a7 + 96));
          v84 = v67;
          if ( P && v67 >= 0 )
            memmove(v116, P, (unsigned int)v101);
          NtfsReservedUnmapBuffer(v117, v125);
          v43 = v84;
          if ( v84 < 0 )
            goto LABEL_80;
          v57 = v101 + Size;
          Size += (unsigned int)v101;
          v56 = v89;
        }
        if ( v43 >= 0 && v44 != v57 )
        {
          v79[0] = 0;
          NtfsFillMdl(a1, v96, v44 - v57, NumberOfBytes_4 + v57 + *Src, *(_DWORD *)v79);
          v43 = v84;
        }
      }
    }
    else
    {
      v79[0] = 0;
      NtfsFillMdl(a1, v96, v39, *(_DWORD *)(a7 + 64) + NumberOfBytes_4, *(_DWORD *)v79);
      v43 = v84;
      v44 = NumberOfBytes;
    }
LABEL_147:
    if ( P )
    {
      ExFreePoolWithTag(P, 0);
      P = 0;
      v43 = v84;
    }
    if ( v83 )
    {
      KeReleaseGuardedMutex(&stru_140095940);
      v83 = 0;
      *(_QWORD *)(a7 + 96) = 0;
      v43 = v84;
    }
    if ( v43 < 0 )
      break;
    v26 += v123;
    v113 = v26;
    v97 = 0;
    NumberOfBytes_4 += v44;
    v92 += v91;
    v29 = a5 - v44;
    a5 -= v44;
  }
  LOBYTE(v32) = 1;
  KeFlushIoBuffers(*v124, v32, 0);
  v12 = v84;
LABEL_153:
  LOBYTE(a2) = 1;
  KeFlushIoBuffers(*(_QWORD *)(a7 + 48), a2, 0);
  return v12;
}

```

## disassembly

```asm
0x140177be0  push    rbx
0x140177be2  push    rsi
0x140177be3  push    rdi
0x140177be4  push    r12
0x140177be6  push    r13
0x140177be8  push    r14
0x140177bea  push    r15
0x140177bec  sub     rsp, 1D0h
0x140177bf3  mov     rax, cs:__security_cookie
0x140177bfa  xor     rax, rsp
0x140177bfd  mov     [rsp+208h+var_48], rax
0x140177c05  mov     r13, r9
0x140177c08  mov     r15, r8
0x140177c0b  mov     r11, rdx
0x140177c0e  mov     [rsp+208h+var_178], rdx
0x140177c16  mov     rsi, rcx
0x140177c19  mov     [rsp+208h+var_C0], rcx
0x140177c21  mov     [rsp+208h+var_B8], rdx
0x140177c29  mov     [rsp+208h+var_B0], r8
0x140177c31  mov     rdi, [rsp+208h+arg_30]
0x140177c39  mov     [rsp+208h+var_E8], rdi
0x140177c41  xor     ebx, ebx
0x140177c43  mov     [rsp+208h+var_140], rbx
0x140177c4b  mov     [rsp+208h+var_130], rbx
0x140177c53  mov     [rsp+208h+Size], rbx
0x140177c5b  mov     [rsp+208h+var_158], rbx
0x140177c63  mov     r12d, ebx
0x140177c66  mov     r14, [r8+0C0h]
0x140177c6d  mov     [rsp+208h+var_100], r14
0x140177c75  mov     [rsp+208h+var_C8], r14
0x140177c7d  cmp     byte ptr [rcx+20h], 3
0x140177c81  jz      loc_140177D11
0x140177c87  cmp     [rdi+69h], bl
0x140177c8a  jnz     loc_140178BF2
0x140177c90  cmp     r11, [rsi+70h]
0x140177c94  jnz     loc_140178A8E
0x140177c9a  cmp     dword ptr [rdi+44h], 0
0x140177c9e  jnz     loc_140178A8E
0x140177ca4  cmp     byte ptr [rdi+6Bh], 0
0x140177ca8  jz      loc_140178E13
0x140177cae  xor     r14b, r14b
0x140177cb1  mov     rcx, rsi
0x140177cb4  call    NtfsCheckpointCurrentTransaction
0x140177cb9  and     dword ptr [rsi+4], 0FFFFDFFFh
0x140177cc0  lea     rbx, [rsi+98h]
0x140177cc7  mov     rax, [rbx]
0x140177cca  cmp     rax, rbx
0x140177ccd  jz      loc_140178AB5
0x140177cd3  mov     rcx, [r15+0B8h]
0x140177cda  lea     rdx, [rax-50h]
0x140177cde  cmp     rdx, rcx
0x140177ce1  jnz     loc_140179017
0x140177ce7  lea     rax, [rcx+50h]
0x140177ceb  mov     rdx, [rax]
0x140177cee  cmp     [rdx+8], rax
0x140177cf2  jnz     loc_140178AC8
0x140177cf8  mov     r8, [rcx+58h]
0x140177cfc  cmp     [r8], rax
0x140177cff  jnz     loc_140178AC8
0x140177d05  mov     [r8], rdx
0x140177d08  mov     [rdx+8], r8
0x140177d0c  mov     r14b, 1
0x140177d0f  jmp     short loc_140177CC7
0x140177d11  cmp     [r8+1F8h], rbx
0x140177d18  jnz     loc_140178F3A
0x140177d1e  lea     rcx, [r15+1CCh]
0x140177d25  mov     [rsp+208h+var_138], rcx
0x140177d2d  cmp     [rcx], bl
0x140177d2f  jz      loc_140178F87
0x140177d35  cmp     [rdi+44h], ebx
0x140177d38  jnz     loc_140178A79
0x140177d3e  mov     [rsp+208h+var_E0], rdi
0x140177d46  mov     [rsp+208h+var_A8], rcx
0x140177d4e  mov     [rsp+208h+var_1B7], bl
0x140177d52  mov     [rsp+208h+P], rbx
0x140177d57  mov     eax, [r15+1C4h]
0x140177d5e  mov     [rsp+208h+var_164], eax
0x140177d65  mov     [rsp+208h+var_11C], eax
0x140177d6c  lea     rcx, [r14+1E8h]
0x140177d73  mov     [rsp+208h+var_110], rcx
0x140177d7b  mov     ecx, [rcx]
0x140177d7d  mov     edx, [r14+1E0h]
0x140177d84  lea     r12d, [rdx+rax]
0x140177d88  shr     r12d, cl
0x140177d8b  mov     [rsp+208h+var_18C], ebx
0x140177d8f  mov     dword ptr [rsp+208h+NumberOfBytes+4], ebx
0x140177d93  mov     [rsp+208h+var_1B4], ebx
0x140177d97  lea     r8, [rdi+30h]
0x140177d9b  mov     [rsp+208h+var_98], r8
0x140177da3  mov     r8, [r8]
0x140177da6  mov     [rsp+208h+var_170], r8
0x140177dae  test    r8, r8
0x140177db1  jz      loc_140178CC9
0x140177db7  mov     [rsp+208h+var_F8], r8
0x140177dbf  dec     eax
0x140177dc1  mov     [rsp+208h+CompressFragmentWorkSpaceSize], eax
0x140177dc8  mov     r8d, r13d
0x140177dcb  and     r8d, eax
0x140177dce  mov     [rsp+208h+var_168], r8d
0x140177dd6  mov     r14, rdx
0x140177dd9  mov     eax, r8d
0x140177ddc  sub     r14, rax
0x140177ddf  add     r14, r13
0x140177de2  sar     r14, cl
0x140177de5  mov     [rsp+208h+var_F0], r14
0x140177ded  lea     rax, [rsp+208h+var_158]
0x140177df5  mov     qword ptr [rsp+208h+var_1E8], rax
0x140177dfa  lea     r9, [rsp+208h+var_140]
0x140177e02  mov     r8, r14
0x140177e05  mov     rdx, r15
0x140177e08  mov     rcx, rsi
0x140177e0b  call    NtfsLookupAllocation
0x140177e10  test    al, al
0x140177e12  jz      loc_140178F8E
0x140177e18  mov     rdx, [rsp+208h+var_140]
0x140177e20  mov     rax, 7FFFFFFFFFFFFFFFh
0x140177e2a  sub     rax, r14
0x140177e2d  mov     rcx, [rsp+208h+var_158]
0x140177e35  cmp     rcx, rax
0x140177e38  jge     loc_140178B31
0x140177e3e  mov     [rsp+208h+var_1B0], 1
0x140177e43  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140177e47  jz      loc_140178B35
0x140177e4d  lea     rax, [rcx+r14]
0x140177e51  mov     [rsp+208h+var_148], rax
0x140177e59  mov     [rsp+208h+var_130], rbx
0x140177e61  movsxd  rdx, [rsp+208h+CompressFragmentWorkSpaceSize]
0x140177e69  mov     r8d, [rsp+208h+arg_20]
0x140177e71  add     rdx, r13
0x140177e74  add     rdx, r8
0x140177e77  mov     r13d, [rsp+208h+var_164]
0x140177e7f  mov     eax, r13d
0x140177e82  neg     eax
0x140177e84  movsxd  rcx, eax
0x140177e87  and     rdx, rcx
0x140177e8a  mov     rcx, [rsp+208h+var_110]
0x140177e92  movzx   ecx, byte ptr [rcx]
0x140177e95  sar     rdx, cl
0x140177e98  mov     [rsp+208h+var_108], rdx
0x140177ea0  mov     eax, r12d
0x140177ea3  mov     [rsp+208h+var_118], rax
0x140177eab  test    r8d, r8d
0x140177eae  jz      loc_140178A58
0x140177eb4  mov     rdx, [rsp+208h+var_178]
0x140177ebc  mov     rcx, rdi
0x140177ebf  call    NtfsMapCompressionContext
0x140177ec4  mov     r12, rax
0x140177ec7  test    rax, rax
0x140177eca  jz      short loc_140177ED2
0x140177ecc  mov     ecx, [rdi+40h]
0x140177ecf  add     r12, rcx
0x140177ed2  mov     rcx, [rsp+208h+var_130]
0x140177eda  movzx   eax, [rsp+208h+var_1B0]
0x140177edf  mov     r10, [rsp+208h+var_148]
0x140177ee7  mov     rdx, [rsp+208h+var_158]
0x140177eef  mov     r8, [rsp+208h+var_118]
0x140177ef7  test    al, al
0x140177ef9  jz      short loc_140177F04
0x140177efb  cmp     rdx, r8
0x140177efe  jl      loc_140178B45
0x140177f04  mov     rax, r8
0x140177f07  mov     [rsp+208h+var_A0], rax
0x140177f0f  cmp     rdx, r8
0x140177f12  jl      loc_140178ACF
0x140177f18  mov     r8d, r13d
0x140177f1b  mov     [rsp+208h+var_190], r13d
0x140177f20  sub     rdx, rax
0x140177f23  mov     [rsp+208h+var_158], rdx
0x140177f2b  mov     eax, r13d
0x140177f2e  mov     ecx, [rsp+208h+var_168]
0x140177f35  sub     eax, ecx
0x140177f37  mov     edx, [rsp+208h+arg_20]
0x140177f3e  cmp     eax, edx
0x140177f40  cmovbe  edx, eax
0x140177f43  mov     dword ptr [rsp+208h+NumberOfBytes], edx
0x140177f47  mov     [rsp+208h+var_120], edx
0x140177f4e  test    r8d, r8d
0x140177f51  jz      loc_1401782DB
0x140177f57  cmp     r8d, r13d
0x140177f5a  jz      loc_14017825B
0x140177f60  test    r12, r12
0x140177f63  jz      loc_140178500
0x140177f69  mov     [rsp+208h+var_1B8], 0
0x140177f6e  cmp     edx, r13d
0x140177f71  jb      loc_140178047
0x140177f77  mov     edx, 2
0x140177f7c  mov     rcx, [rsp+208h+var_170]
0x140177f84  call    cs:__imp_MmMdlPageContentsState
0x140177f8b  nop     dword ptr [rax+rax+00h]
0x140177f90  cmp     eax, 1
0x140177f93  jnz     loc_140178885
0x140177f99  mov     eax, dword ptr [rsp+208h+NumberOfBytes+4]
0x140177f9d  add     rax, r12
0x140177fa0  mov     [rsp+208h+Src], rax
0x140177fa8  mov     r9d, [rsp+208h+var_18C]
0x140177fad  add     r9, [rdi+20h]
0x140177fb1  mov     rcx, [rsp+208h+var_138]
0x140177fb9  movzx   ecx, word ptr [rcx]
0x140177fbc  mov     edx, 0FFh
0x140177fc1  and     cx, dx
0x140177fc4  inc     cx
0x140177fc7  mov     [rsp+208h+var_1D0], rbx
0x140177fcc  lea     rdx, [rsp+208h+Size]
0x140177fd4  mov     [rsp+208h+var_1D8], rdx
0x140177fd9  mov     dword ptr [rsp+208h+var_1E0], 1000h
0x140177fe1  mov     edx, [rsp+208h+var_190]
0x140177fe5  mov     dword ptr [rsp+208h+var_1E8], edx
0x140177fe9  mov     r8d, dword ptr [rsp+208h+NumberOfBytes]
0x140177fee  mov     rdx, rax
0x140177ff1  call    cs:__imp_RtlDecompressBufferEx2
0x140177ff8  nop     dword ptr [rax+rax+00h]
0x140177ffd  mov     ecx, eax
0x140177fff  mov     [rsp+208h+var_1B4], eax
0x140178003  mov     [rsp+208h+var_1A4], eax
0x140178007  cmp     [rsp+208h+P], 0
0x14017800d  jnz     loc_1401788D7
0x140178013  test    ecx, ecx
0x140178015  js      loc_140178480
0x14017801b  mov     r8d, dword ptr [rsp+208h+NumberOfBytes]
0x140178020  mov     rcx, [rsp+208h+Size]
0x140178028  sub     r8d, ecx; Size
0x14017802b  add     ecx, dword ptr [rsp+208h+NumberOfBytes+4]
0x14017802f  add     rcx, r12; void *
0x140178032  xor     edx, edx; Val
0x140178034  call    memset
0x140178039  mov     ecx, [rsp+208h+var_1B4]
0x14017803d  mov     r12d, dword ptr [rsp+208h+NumberOfBytes]
0x140178042  jmp     loc_140178913
0x140178047  cmp     qword ptr [rdi+60h], 0
0x14017804c  jz      loc_1401781AE
0x140178052  mov     edx, 2
0x140178057  mov     rcx, [rsp+208h+var_170]
0x14017805f  call    cs:__imp_MmMdlPageContentsState
0x140178066  nop     dword ptr [rax+rax+00h]
0x14017806b  cmp     eax, 1
0x14017806e  jnz     loc_1401782A2
0x140178074  mov     edx, dword ptr [rsp+208h+NumberOfBytes+4]
0x140178078  add     rdx, r12
0x14017807b  mov     [rsp+208h+Src], rdx
0x140178083  mov     r9d, [rsp+208h+var_18C]
0x140178088  add     r9, [rdi+20h]
0x14017808c  mov     rax, [rsp+208h+var_138]
0x140178094  movzx   ecx, word ptr [rax]
0x140178097  mov     eax, 0FFh
0x14017809c  and     cx, ax
0x14017809f  inc     cx
0x1401780a2  mov     rax, [rdi+60h]
0x1401780a6  mov     [rsp+208h+var_1C8], rax
0x1401780ab  lea     rax, [rsp+208h+Size]
0x1401780b3  mov     [rsp+208h+var_1D0], rax
0x1401780b8  mov     dword ptr [rsp+208h+var_1D8], 1000h
0x1401780c0  mov     eax, [rsp+208h+var_168]
0x1401780c7  mov     dword ptr [rsp+208h+var_1E0], eax
0x1401780cb  mov     eax, [rsp+208h+var_190]
0x1401780cf  mov     dword ptr [rsp+208h+var_1E8], eax
0x1401780d3  mov     r8d, dword ptr [rsp+208h+NumberOfBytes]
0x1401780d8  call    cs:__imp_RtlDecompressFragmentEx
0x1401780df  nop     dword ptr [rax+rax+00h]
0x1401780e4  mov     ecx, eax
0x1401780e6  mov     [rsp+208h+var_1B4], eax
0x1401780ea  mov     [rsp+208h+var_1A4], eax
0x1401780ee  cmp     [rsp+208h+P], 0
0x1401780f4  jz      short loc_140178126
0x1401780f6  test    eax, eax
0x1401780f8  js      loc_140178292
0x1401780fe  mov     r8d, dword ptr [rsp+208h+NumberOfBytes]
0x140178103  test    eax, eax
0x140178105  cmovns  r8d, dword ptr [rsp+208h+Size]; Size
0x14017810e  mov     ecx, dword ptr [rsp+208h+NumberOfBytes+4]
0x140178112  add     rcx, r12; void *
0x140178115  mov     rdx, [rsp+208h+Src]; Src
0x14017811d  call    memmove
0x140178122  mov     ecx, [rsp+208h+var_1B4]
0x140178126  test    ecx, ecx
0x140178128  jns     loc_14017801B
0x14017812e  movzx   eax, cs:NtfsStatusDebugFlags
0x140178135  test    al, al
0x140178137  jz      short loc_140178170
0x140178139  cmp     ecx, 0FFFFFFEDh
0x14017813c  jnb     short loc_140178170
0x14017813e  cmp     ecx, 0C0000016h
0x140178144  jz      short loc_140178170
0x140178146  cmp     ecx, 0C0000011h
0x14017814c  jz      short loc_140178170
0x14017814e  lea     eax, [rcx+7FFFFFFBh]
0x140178154  cmp     eax, 1
0x140178157  jbe     short loc_140178170
0x140178159  cmp     ecx, 0C00000D8h
0x14017815f  jz      short loc_140178170
0x140178161  mov     r8d, 0C1FFDh
0x140178167  mov     edx, ecx
0x140178169  xor     ecx, ecx
0x14017816b  call    NtfsStatusTraceAndDebugInternal
0x140178170  mov     ecx, ebx
0x140178172  mov     [rsp+208h+var_1B4], ebx
0x140178176  mov     [rsp+208h+var_1A4], ebx
0x14017817a  cmp     [rsp+208h+var_1B8], 0
0x14017817f  jnz     loc_14017803D
0x140178185  mov     r8d, dword ptr [rsp+208h+NumberOfBytes]; Size
0x14017818a  mov     edx, 0DFh; Val
  ... truncated ...
```
