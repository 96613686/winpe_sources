# NtfsFinishBuffers

- ea: `0x140177be0`
- end: `0x140179027`
- name: `NtfsFinishBuffers`
- size: `5191`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, unsigned int, __int64)`
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
        unsigned int a6,
        __int64 a7)
{
  __int64 v9; // r11
  LONGLONG v11; // rbx
  int v12; // r12d
  __int64 v13; // r14
  char v14; // r14
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // r8
  ULONG v20; // eax
  int v21; // ecx
  __int64 v22; // rdx
  unsigned int v23; // r12d
  struct _MDL *v24; // r8
  LONGLONG v25; // r14
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int v28; // r8d
  __int64 v29; // rdx
  ULONG v30; // r13d
  __int64 i; // rdx
  char *v32; // rax
  char *v33; // r12
  __int64 v34; // rcx
  char v35; // al
  LONGLONG v36; // r10
  ULONG v37; // r8d
  unsigned int v38; // edx
  char *v39; // rax
  int v40; // eax
  signed int v41; // ecx
  int v42; // ecx
  unsigned int v43; // r12d
  char *v44; // rdx
  int v45; // eax
  signed int v46; // ecx
  size_t v47; // r8
  NTSTATUS CompressionWorkSpaceSize; // eax
  int v49; // edx
  PVOID PoolWithTag; // rax
  PVOID v51; // rax
  int v52; // edx
  unsigned int v53; // r8d
  __int64 v54; // rax
  unsigned int v55; // edx
  int v56; // r8d
  int v57; // eax
  NTSTATUS v58; // eax
  PVOID v59; // rax
  unsigned int v60; // eax
  unsigned int v61; // eax
  ULONG v62; // eax
  PVOID v63; // rcx
  __int64 v64; // r8
  PVOID v65; // rdx
  int v66; // eax
  size_t v67; // r8
  __int64 v69; // rdx
  __int64 v70; // rax
  char v71; // cl
  int v72; // r8d
  __int64 v73; // r9
  __int64 v74; // rdx
  __int64 v75; // rax
  __int64 v76; // rax
  _QWORD *v77; // rcx
  __int64 v78; // [rsp+20h] [rbp-1E8h]
  __int64 v79; // [rsp+30h] [rbp-1D8h]
  char v80; // [rsp+50h] [rbp-1B8h]
  char v81; // [rsp+51h] [rbp-1B7h]
  signed int v82; // [rsp+54h] [rbp-1B4h]
  char v83; // [rsp+58h] [rbp-1B0h]
  unsigned int NumberOfBytes; // [rsp+5Ch] [rbp-1ACh]
  int NumberOfBytesa; // [rsp+5Ch] [rbp-1ACh]
  int NumberOfBytes_4; // [rsp+60h] [rbp-1A8h]
  NTSTATUS v87; // [rsp+64h] [rbp-1A4h]
  unsigned int v88; // [rsp+68h] [rbp-1A0h]
  PVOID P; // [rsp+70h] [rbp-198h]
  ULONG v90; // [rsp+78h] [rbp-190h]
  unsigned int v91; // [rsp+7Ch] [rbp-18Ch]
  char *Src; // [rsp+80h] [rbp-188h]
  char *Srca; // [rsp+80h] [rbp-188h]
  _DWORD *Srcb; // [rsp+80h] [rbp-188h]
  size_t Size; // [rsp+88h] [rbp-180h] BYREF
  __int64 v96; // [rsp+90h] [rbp-178h]
  struct _MDL *v97; // [rsp+98h] [rbp-170h]
  unsigned int v98; // [rsp+A0h] [rbp-168h]
  ULONG v99; // [rsp+A4h] [rbp-164h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+A8h] [rbp-160h] BYREF
  __int64 v101; // [rsp+B0h] [rbp-158h] BYREF
  size_t v102; // [rsp+B8h] [rbp-150h] BYREF
  LONGLONG v103; // [rsp+C0h] [rbp-148h]
  __int64 v104; // [rsp+C8h] [rbp-140h] BYREF
  _WORD *v105; // [rsp+D0h] [rbp-138h]
  __int64 v106; // [rsp+D8h] [rbp-130h] BYREF
  ULONG v107; // [rsp+E0h] [rbp-128h] BYREF
  ULONG CompressBufferWorkSpaceSize[3]; // [rsp+E4h] [rbp-124h] BYREF
  __int64 v109; // [rsp+F0h] [rbp-118h]
  _BYTE *v110; // [rsp+F8h] [rbp-110h]
  LONGLONG v111; // [rsp+100h] [rbp-108h]
  __int64 v112; // [rsp+108h] [rbp-100h]
  struct _MDL *v113; // [rsp+110h] [rbp-F8h]
  LONGLONG v114; // [rsp+118h] [rbp-F0h]
  __int64 v115; // [rsp+120h] [rbp-E8h]
  __int64 v116; // [rsp+128h] [rbp-E0h]
  void *v117; // [rsp+130h] [rbp-D8h]
  __int64 v118; // [rsp+138h] [rbp-D0h]
  __int64 v119; // [rsp+140h] [rbp-C8h]
  __int64 v120; // [rsp+148h] [rbp-C0h]
  __int64 v121; // [rsp+150h] [rbp-B8h]
  __int64 v122; // [rsp+158h] [rbp-B0h]
  __int64 v123; // [rsp+160h] [rbp-A8h]
  __int64 v124; // [rsp+168h] [rbp-A0h]
  _QWORD *v125; // [rsp+170h] [rbp-98h]
  _BYTE v126[64]; // [rsp+180h] [rbp-88h] BYREF

  v9 = a2;
  v96 = a2;
  v120 = a1;
  v121 = a2;
  v122 = a3;
  v115 = a7;
  v11 = 0;
  v104 = 0;
  v106 = 0;
  Size = 0;
  v101 = 0;
  v12 = 0;
  v13 = *(_QWORD *)(a3 + 192);
  v112 = v13;
  v119 = v13;
  if ( *(_BYTE *)(a1 + 32) != 3 )
  {
    if ( !*(_BYTE *)(a7 + 105) )
      goto LABEL_3;
    v70 = *(_QWORD *)(a1 + 192);
    if ( !v70 || *(_QWORD *)(v70 + 80) != a3 )
      goto LABEL_3;
    v71 = 0;
    v72 = *(_DWORD *)(a3 + 452);
    v73 = -v72;
    v74 = a4 & v73;
    v75 = a5 + a4;
    v103 = v75;
    if ( v75 < *(_QWORD *)(a7 + 24) )
    {
      v76 = v73 & v75;
      v103 = v76;
      if ( v76 <= v74 )
        goto LABEL_179;
      v12 = NtfsPersistDelayedAllocation(a1, v74 >> *(_BYTE *)(v13 + 488), (v76 >> *(_BYTE *)(v13 + 488)) - 1, 0, v78);
      if ( v12 < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)v12 < 0xFFFFFFED
          && v12 != -1073741802
          && v12 != -1073741807
          && (unsigned int)(v12 + 2147483643) > 1
          && v12 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v12, 0xC2155u);
        }
        NtfsRaiseStatusInternal(a1, v12, 0, 0, 794965);
      }
      if ( *(_DWORD *)(a1 + 28) )
      {
        if ( *(_BYTE *)(a3 + 460) )
        {
          if ( (*(_DWORD *)(v13 + 24) & 0x8000000) != 0 && !(unsigned __int8)NtfsReserveClusters(a1, 1) )
          {
            NtfsAllocateDiskFullContext(a1, a5, 0x274000C216ELL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 0xC000007F, 0xC216Fu);
            NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 794991);
          }
          v11 = v103;
        }
        v71 = 1;
        goto LABEL_178;
      }
    }
    else
    {
      v12 = NtfsPersistDelayedAllocation(
              a1,
              v74 >> *(_BYTE *)(v13 + 488),
              ((v73 & (a5 + a4 + v72 - 1)) >> *(_BYTE *)(v13 + 488)) - 1,
              0,
              v78);
      if ( v12 < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)v12 < 0xFFFFFFED
          && v12 != -1073741802
          && v12 != -1073741807
          && (unsigned int)(v12 + 2147483643) > 1
          && v12 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v12, 0xC211Bu);
        }
        NtfsRaiseStatusInternal(a1, v12, 0, 0, 794907);
      }
      if ( *(_DWORD *)(a1 + 28) && *(_BYTE *)(a3 + 460) )
      {
        if ( (*(_DWORD *)(v13 + 24) & 0x8000000) != 0 && !(unsigned __int8)NtfsReserveClusters(a1, 1) )
        {
          NtfsAllocateDiskFullContext(a1, a5, 0x273000C2137LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC000007F, 0xC2138u);
          NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 794936);
        }
        v11 = v103;
      }
    }
    v71 = 0;
LABEL_178:
    v9 = v96;
LABEL_179:
    if ( v11 > *(_QWORD *)(a3 + 464) )
      *(_QWORD *)(a3 + 464) = v11;
    if ( v71 )
    {
      NtfsCheckpointCurrentTransaction(a1);
      v9 = v96;
    }
LABEL_3:
    if ( v9 == *(_QWORD *)(a1 + 112) && !*(_DWORD *)(a7 + 68) )
    {
      if ( *(_BYTE *)(a7 + 107) )
      {
        v14 = 0;
        NtfsCheckpointCurrentTransaction(a1);
        *(_DWORD *)(a1 + 4) &= ~0x2000u;
        v15 = (_QWORD *)(a1 + 152);
        while ( 1 )
        {
          v16 = (_QWORD *)*v15;
          if ( (_QWORD *)*v15 == v15 )
            break;
          v17 = *(_QWORD **)(a3 + 184);
          if ( v16 - 10 == v17 )
          {
            v18 = v17[10];
            if ( *(_QWORD **)(v18 + 8) != v17 + 10 )
              goto LABEL_157;
            v19 = (_QWORD *)v17[11];
            if ( (_QWORD *)*v19 != v17 + 10 )
              goto LABEL_157;
            *v19 = v18;
            *(_QWORD *)(v18 + 8) = v19;
            v14 = 1;
          }
          else
          {
            NtfsReleaseFcbEx(a1, (__int64)(v16 - 10), 0);
          }
        }
        if ( v14 )
        {
          if ( (_QWORD *)v16[1] != v15 )
LABEL_157:
            __fastfail(3u);
          v77 = (_QWORD *)(*(_QWORD *)(a3 + 184) + 80LL);
          *v77 = v16;
          v77[1] = v15;
          v16[1] = v77;
          *v15 = v77;
          NtfsDeallocateCompressionBuffer(a1, v96, a7, 1);
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          *(_BYTE *)(a7 + 107) = 0;
        }
      }
      *(_BYTE *)(a7 + 109) = 0;
    }
    return (unsigned int)v12;
  }
  if ( *(_QWORD *)(a3 + 504) && *(int *)(a3 + 200) >= 0 && *(_DWORD *)(a3 + 256) == 128 && xmmword_140095740 )
  {
    NtfsDecryptBuffers(a1, a2, a3, a4, a6, a7);
    v9 = v96;
  }
  v105 = (_WORD *)(a3 + 460);
  if ( *(_BYTE *)(a3 + 460) )
  {
    if ( *(_DWORD *)(a7 + 68) )
    {
LABEL_153:
      LOBYTE(a2) = 1;
      KeFlushIoBuffers(*(_QWORD *)(a7 + 48), a2, 0);
      return (unsigned int)v12;
    }
    v116 = a7;
    v123 = a3 + 460;
    v81 = 0;
    P = 0;
    v20 = *(_DWORD *)(a3 + 452);
    v99 = v20;
    CompressBufferWorkSpaceSize[2] = v20;
    v110 = (_BYTE *)(v13 + 488);
    v21 = *(_DWORD *)(v13 + 488);
    v22 = *(unsigned int *)(v13 + 480);
    v23 = ((unsigned int)v22 + v20) >> v21;
    v91 = 0;
    NumberOfBytes_4 = 0;
    v82 = 0;
    v125 = (_QWORD *)(a7 + 48);
    v24 = *(struct _MDL **)(a7 + 48);
    v97 = v24;
    if ( !v24 )
    {
      v24 = *(struct _MDL **)(v9 + 8);
      v97 = v24;
    }
    v113 = v24;
    CompressFragmentWorkSpaceSize = v20 - 1;
    v98 = (v20 - 1) & a4;
    v25 = (a4 + v22 - v98) >> v21;
    v114 = v25;
    if ( (unsigned __int8)NtfsLookupAllocation(a1, a3, v25, &v104, &v101) )
    {
      v26 = v104;
    }
    else
    {
      v26 = -1;
      v104 = -1;
    }
    v27 = v101;
    if ( v101 >= 0x7FFFFFFFFFFFFFFFLL - v25 )
    {
      v83 = 0;
    }
    else
    {
      v83 = 1;
      if ( v26 != -1 )
        goto LABEL_21;
    }
    v27 = 0;
    v101 = 0;
LABEL_21:
    v103 = v27 + v25;
    v106 = 0;
    v28 = a5;
    v29 = a5 + a4 + (int)CompressFragmentWorkSpaceSize;
    v30 = v99;
    i = (__int64)(-v99 & (unsigned __int64)v29) >> *v110;
    v111 = i;
    v109 = v23;
    while ( v28 )
    {
      v32 = (char *)NtfsMapCompressionContext(a7, v96);
      v33 = v32;
      if ( v32 )
        v33 = &v32[*(unsigned int *)(a7 + 64)];
      v34 = v106;
      v35 = v83;
      v36 = v103;
LABEL_26:
      while ( v35 && v101 < v109 && v101 + v25 == v36 )
      {
        v101 += v34;
        while ( 1 )
        {
          v36 += v34;
          v103 = v36;
          if ( v36 >= v111 )
          {
            v35 = 1;
            v83 = 1;
            goto LABEL_26;
          }
          if ( (unsigned __int8)NtfsLookupAllocation(a1, a3, v36, &v104, &v106) )
          {
            v69 = v104;
          }
          else
          {
            v69 = -1;
            v104 = -1;
          }
          v36 = v103;
          v34 = v106;
          if ( v106 >= 0x7FFFFFFFFFFFFFFFLL - v103 )
            break;
          v35 = 1;
          v83 = 1;
          if ( v69 != -1 )
            goto LABEL_26;
        }
        v35 = 0;
        v83 = 0;
      }
      v124 = v109;
      if ( v101 < v109 )
      {
        v37 = (_DWORD)v101 << *(_DWORD *)v110;
        v90 = v37;
        v101 = 0;
      }
      else
      {
        v37 = v30;
        v90 = v30;
        v101 -= v109;
      }
      v38 = a5;
      if ( v30 - v98 <= a5 )
        v38 = v30 - v98;
      NumberOfBytes = v38;
      CompressBufferWorkSpaceSize[1] = v38;
      if ( v37 )
      {
        if ( v37 == v30 )
        {
          NtfsCopyIntoMdl(
            a1,
            (__int64)v97,
            v38,
            *(_DWORD *)(a7 + 64) + NumberOfBytes_4,
            (char *)(*(_QWORD *)(a7 + 32) + v91 + v98));
          v42 = v82;
          v43 = NumberOfBytes;
        }
        else if ( v33 )
        {
          v80 = 0;
          if ( v38 < v30 )
          {
            if ( !*(_QWORD *)(a7 + 96) )
            {
              CompressBufferWorkSpaceSize[0] = 0;
              CompressFragmentWorkSpaceSize = 0;
              CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                           (unsigned __int8)*v105 + 1,
                                           CompressBufferWorkSpaceSize,
                                           &CompressFragmentWorkSpaceSize);
              v49 = CompressionWorkSpaceSize;
              v87 = CompressionWorkSpaceSize;
              if ( CompressionWorkSpaceSize < 0 )
              {
                if ( NtfsStatusDebugFlags
                  && (unsigned int)CompressionWorkSpaceSize < 0xFFFFFFED
                  && CompressionWorkSpaceSize != -1073741802
                  && CompressionWorkSpaceSize != -1073741807
                  && (unsigned int)(CompressionWorkSpaceSize + 2147483643) > 1
                  && CompressionWorkSpaceSize != -1073741608 )
                {
                  NtfsStatusTraceAndDebugInternal(a1, CompressionWorkSpaceSize, 0xC1F90u);
                  v49 = v87;
                }
                NtfsRaiseStatusInternal(a1, v49, 0, 0, 794512);
              }
              if ( CompressFragmentWorkSpaceSize )
              {
                PoolWithTag = ExAllocatePoolWithTag(PoolType, CompressFragmentWorkSpaceSize, 0x4446744Eu);
                *(_QWORD *)(a7 + 96) = PoolWithTag;
                if ( !PoolWithTag )
                {
                  KeAcquireGuardedMutex(&stru_140095940);
                  v81 = 1;
                  *(_QWORD *)(a7 + 96) = qword_1400959A8;
                }
              }
            }
            if ( (unsigned int)MmMdlPageContentsState(v97, 2) == 1 )
            {
              v44 = &v33[NumberOfBytes_4];
              Srca = v44;
            }
            else
            {
              v51 = ExAllocatePoolWithTag((POOL_TYPE)512, NumberOfBytes, 0x4446744Eu);
              P = v51;
              if ( !v51 )
              {
                v51 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), NumberOfBytes, 0x4446744Eu);
                P = v51;
              }
              v44 = (char *)v51;
              Srca = (char *)v51;
            }
            while ( 1 )
            {
              LODWORD(v79) = 4096;
              v45 = RtlDecompressFragmentEx(
                      (unsigned __int16)((unsigned __int8)*v105 + 1),
                      v44,
                      NumberOfBytes,
                      *(_QWORD *)(a7 + 32) + v91,
                      v90,
                      v98,
                      v79,
                      &Size,
                      *(_QWORD *)(a7 + 96));
              v46 = v45;
              v82 = v45;
              if ( P && (v45 >= 0 || v80) )
              {
                v47 = NumberOfBytes;
                if ( v45 >= 0 )
                  v47 = (unsigned int)Size;
                memmove(&v33[NumberOfBytes_4], Srca, v47);
                v46 = v82;
              }
              if ( v46 >= 0 )
                break;
              if ( NtfsStatusDebugFlags
                && (unsigned int)v46 < 0xFFFFFFED
                && v46 != -1073741802
                && v46 != -1073741807
                && (unsigned int)(v46 + 2147483643) > 1
                && v46 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(0, v46, 0xC1FFDu);
              }
              v42 = 0;
              v82 = 0;
              if ( v80 )
                goto LABEL_42;
              memset(Srca, 223, NumberOfBytes);
              v80 = 1;
              v44 = Srca;
            }
          }
          else
          {
            if ( (unsigned int)MmMdlPageContentsState(v97, 2) == 1 )
            {
              v39 = &v33[NumberOfBytes_4];
            }
            else
            {
              v39 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, NumberOfBytes, 0x4446744Eu);
              P = v39;
              if ( !v39 )
              {
                v39 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), NumberOfBytes, 0x4446744Eu);
                P = v39;
              }
            }
            for ( Src = v39; ; v39 = Src )
            {
              v40 = RtlDecompressBufferEx2(
                      (unsigned __int16)((unsigned __int8)*v105 + 1),
                      v39,
                      NumberOfBytes,
                      *(_QWORD *)(a7 + 32) + v91,
                      v90,
                      4096,
                      &Size,
                      0);
              v41 = v40;
              v82 = v40;
              if ( P && (v40 >= 0 || v80) )
              {
                v67 = NumberOfBytes;
                if ( v40 >= 0 )
                  v67 = (unsigned int)Size;
                memmove(&v33[NumberOfBytes_4], Src, v67);
                v41 = v82;
              }
              if ( v41 >= 0 )
                break;
              if ( NtfsStatusDebugFlags
                && (unsigned int)v41 < 0xFFFFFFED
                && v41 != -1073741802
                && v41 != -1073741807
                && (unsigned int)(v41 + 2147483643) > 1
                && v41 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(0, v41, 0xC2088u);
              }
              v42 = 0;
              v82 = 0;
              if ( v80 )
                goto LABEL_42;
              memset(Src, 219, NumberOfBytes);
              v80 = 1;
            }
          }
          memset(&v33[(unsigned int)(NumberOfBytes_4 + Size)], 0, NumberOfBytes - (unsigned int)Size);
          v42 = v82;
LABEL_42:
          v43 = NumberOfBytes;
        }
        else
        {
          memset(v126, 0, sizeof(v126));
          v43 = NumberOfBytes;
          v88 = NumberOfBytes;
          LODWORD(v102) = 0;
          Size = 0;
          *(_QWORD *)v126 = 0;
          *(_DWORD *)&v126[8] = 64;
          *(_QWORD *)&v126[32] = 0;
          *(_QWORD *)&v126[40] = 0x2000;
          if ( !*(_QWORD *)(a7 + 96) )
          {
            v107 = 0;
            v99 = 0;
            v58 = RtlGetCompressionWorkSpaceSize((unsigned __int8)*v105 + 1, &v107, &v99);
            v52 = v58;
            v82 = v58;
            if ( v58 < 0 )
            {
              if ( NtfsStatusDebugFlags
                && (unsigned int)v58 < 0xFFFFFFED
                && v58 != -1073741802
                && v58 != -1073741807
                && (unsigned int)(v58 + 2147483643) > 1
                && v58 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(a1, v58, 0xC1EDFu);
                v52 = v82;
              }
              NtfsRaiseStatusInternal(a1, v52, 0, 0, 794335);
            }
            if ( v99 )
            {
              v59 = ExAllocatePoolWithTag(PoolType, v99, 0x4446744Eu);
              *(_QWORD *)(a7 + 96) = v59;
              if ( !v59 )
              {
                KeAcquireGuardedMutex(&stru_140095940);
                v81 = 1;
                *(_QWORD *)(a7 + 96) = qword_1400959A8;
              }
            }
          }
          if ( (unsigned int)MmMdlPageContentsState(v97, 2) != 1 )
          {
            v60 = 4096;
            if ( NumberOfBytes < 0x1000 )
              v60 = NumberOfBytes;
            P = ExAllocatePoolWithTag((POOL_TYPE)512, v60, 0x4446744Eu);
            if ( !P )
            {
              v61 = 4096;
              if ( NumberOfBytes < 0x1000 )
                v61 = NumberOfBytes;
              P = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v61, 0x4446744Eu);
            }
          }
          Srcb = (_DWORD *)(v116 + 64);
          v56 = Size;
          v42 = v82;
          for ( i = NumberOfBytes; (_DWORD)i; v88 = i )
          {
            v62 = 4096;
            if ( (unsigned int)i < 0x1000 )
              v62 = i;
            NumberOfBytesa = NumberOfBytes_4 - i;
            v118 = v112 + 5384;
            Srcb = (_DWORD *)(a7 + 64);
            v63 = NtfsReservedMapBuffer(
                    v112 + 5384,
                    v97,
                    (struct _MDL *)v126,
                    *(_DWORD *)(a7 + 64) + NumberOfBytes_4 - i + v43,
                    v62);
            v117 = v63;
            v64 = 4096;
            if ( v88 < 0x1000 )
              v64 = v88;
            v65 = P;
            if ( !P )
              v65 = v63;
            LODWORD(v79) = 4096;
            v66 = RtlDecompressFragmentEx(
                    (unsigned __int16)((unsigned __int8)*v105 + 1),
                    v65,
                    v64,
                    *(_QWORD *)(a7 + 32) + v91,
                    v90,
                    v98 + v43 - v88,
                    v79,
                    &v102,
                    *(_QWORD *)(a7 + 96));
            v82 = v66;
            if ( P && v66 >= 0 )
              memmove(v117, P, (unsigned int)v102);
            NtfsReservedUnmapBuffer(v118, (__int64)v126);
            v42 = v82;
            if ( v82 < 0 )
            {
              if ( NtfsStatusDebugFlags
                && (unsigned int)v82 < 0xFFFFFFED
                && v82 != -1073741802
                && v82 != -1073741807
                && (unsigned int)(v82 + 2147483643) > 1
                && v82 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(0, v82, 0xC1F41u);
              }
              v82 = 0;
              v53 = 4096;
              if ( v88 < 0x1000 )
                v53 = v88;
              NtfsFillMdl(a1, (__int64)v97, v53, *Srcb + v43 + NumberOfBytesa, 0xDFu);
              v54 = 4096;
              v55 = v88;
              if ( v88 < 0x1000 )
                v54 = v88;
              v56 = v54 + Size;
              Size += v54;
              v42 = 0;
            }
            else
            {
              v56 = v102 + Size;
              Size += (unsigned int)v102;
              v55 = v88;
            }
            v57 = v55;
            if ( v55 > 0x1000 )
              v57 = 4096;
            i = v55 - v57;
          }
          if ( v42 >= 0 && v43 != v56 )
          {
            NtfsFillMdl(a1, (__int64)v97, v43 - v56, NumberOfBytes_4 + v56 + *Srcb, 0);
            v42 = v82;
          }
        }
      }
      else
      {
        NtfsFillMdl(a1, (__int64)v97, v38, *(_DWORD *)(a7 + 64) + NumberOfBytes_4, 0);
        v42 = v82;
        v43 = NumberOfBytes;
      }
      if ( P )
      {
        ExFreePoolWithTag(P, 0);
        P = 0;
        v42 = v82;
      }
      if ( v81 )
      {
        KeReleaseGuardedMutex(&stru_140095940);
        v81 = 0;
        *(_QWORD *)(a7 + 96) = 0;
        v42 = v82;
      }
      if ( v42 < 0 )
        break;
      v25 += v124;
      v114 = v25;
      v98 = 0;
      NumberOfBytes_4 += v43;
      v91 += v90;
      v28 = a5 - v43;
      a5 -= v43;
    }
    LOBYTE(i) = 1;
    KeFlushIoBuffers(*v125, i, 0);
    v12 = v82;
    goto LABEL_153;
  }
  return 0;
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
