# TxfReadVersion

- ea: `0x140285a00`
- end: `0x1402864e4`
- name: `TxfReadVersion`
- size: `2788`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14002c840`

## callees

- `0x140007ea0`
- `0x14000ea70`
- `0x140021590`
- `0x140025830`
- `0x1400415b4`
- `0x140052980`
- `0x14005313c`
- `0x140059250`
- `0x1400596c0`
- `0x1400b6e90`
- `0x14010197c`
- `0x1401c00e0`
- `0x140285a00`

## import_xrefs

- `ntoskrnl!CcCopyReadEx` at `0x140285dec`
- `ntoskrnl!CcCopyReadEx` at `0x140286177`
- `ntoskrnl!CcCopyReadEx` at `0x140285dec`
- `ntoskrnl!CcCopyReadEx` at `0x140286177`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285cd5`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285f94`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285cd5`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140285f94`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140285d77`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140285d77`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140285b4a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140285b4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140285b7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140286225`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402863e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bca71`
- `ntoskrnl!ExReleaseResourceLite` at `0x140285b7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140286225`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402863e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bca71`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285c83`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285f3e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402862da`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285c83`
- `ntoskrnl!ExAcquireFastMutex` at `0x140285f3e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402862da`
- `ntoskrnl!ExReleaseFastMutex` at `0x140285cef`
- `ntoskrnl!ExReleaseFastMutex` at `0x140285fb8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402862fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140285cef`
- `ntoskrnl!ExReleaseFastMutex` at `0x140285fb8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402862fb`
- `ntoskrnl!ExRaiseStatus` at `0x140285e40`
- `ntoskrnl!ExRaiseStatus` at `0x1402861ce`
- `ntoskrnl!ExRaiseStatus` at `0x14028649d`
- `ntoskrnl!ExRaiseStatus` at `0x140285e40`
- `ntoskrnl!ExRaiseStatus` at `0x1402861ce`
- `ntoskrnl!ExRaiseStatus` at `0x14028649d`

## pseudocode

```c
void __fastcall TxfReadVersion(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  _QWORD *v7; // rbx
  __int64 v8; // r15
  unsigned int v11; // r12d
  _QWORD *v12; // rdi
  __int64 v13; // r13
  __int64 v14; // r8
  __int64 v15; // rdi
  char v16; // si
  __int64 v17; // r9
  _QWORD *v18; // rdi
  signed __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // ebx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // r8
  unsigned int *v24; // rsi
  __int64 v25; // r9
  __int64 v26; // rdi
  __int64 v27; // rdx
  unsigned int v28; // edi
  __int64 v29; // rsi
  struct _ERESOURCE *v30; // rcx
  __int64 v31; // r8
  NTSTATUS *v32; // rsi
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rdx
  unsigned int v38; // r13d
  _QWORD *v39; // rbx
  __int64 v40; // rsi
  ULONG i; // r9d
  _QWORD *v42; // r10
  unsigned __int64 v43; // r15
  unsigned int v44; // edi
  unsigned int v45; // r9d
  unsigned __int64 v46; // r8
  unsigned int v47; // esi
  unsigned int v48; // r8d
  _QWORD *v49; // rsi
  __int64 v50; // r9
  __int64 j; // rcx
  __int64 v52; // rdx
  NTSTATUS *v53; // rsi
  __int64 v54; // rdx
  unsigned int k; // edx
  unsigned int v56; // edx
  unsigned int v57; // ebx
  unsigned int v58; // edi
  __int64 v59; // rcx
  __int64 v60; // rdx
  char v61; // [rsp+40h] [rbp-148h]
  char v62; // [rsp+41h] [rbp-147h]
  unsigned __int64 v63; // [rsp+48h] [rbp-140h] BYREF
  unsigned int v64; // [rsp+50h] [rbp-138h]
  _QWORD *v65; // [rsp+58h] [rbp-130h]
  unsigned int v66; // [rsp+60h] [rbp-128h]
  ULONG DeleteCount; // [rsp+64h] [rbp-124h] BYREF
  __int64 v68; // [rsp+68h] [rbp-120h]
  int v69; // [rsp+70h] [rbp-118h]
  unsigned int v70; // [rsp+74h] [rbp-114h]
  unsigned __int64 v71; // [rsp+78h] [rbp-110h]
  unsigned int v72; // [rsp+80h] [rbp-108h]
  _DWORD Size[3]; // [rsp+84h] [rbp-104h]
  _QWORD *v74; // [rsp+90h] [rbp-F8h]
  PVOID RestartKey; // [rsp+98h] [rbp-F0h] BYREF
  __int64 v76; // [rsp+A0h] [rbp-E8h]
  __int64 v77; // [rsp+A8h] [rbp-E0h]
  _QWORD *v78; // [rsp+B0h] [rbp-D8h]
  __int64 v79; // [rsp+B8h] [rbp-D0h]
  __int64 v80; // [rsp+C0h] [rbp-C8h]
  __int64 v81; // [rsp+C8h] [rbp-C0h]
  _QWORD *v82; // [rsp+D0h] [rbp-B8h]
  __int64 v83; // [rsp+D8h] [rbp-B0h] BYREF
  unsigned int v84; // [rsp+E0h] [rbp-A8h]
  __int64 v85; // [rsp+E8h] [rbp-A0h]
  __int64 v86; // [rsp+F0h] [rbp-98h]
  __int64 v87; // [rsp+F8h] [rbp-90h]
  __int64 v88; // [rsp+100h] [rbp-88h]
  __int128 MatchData; // [rsp+108h] [rbp-80h] BYREF
  __int128 v90; // [rsp+118h] [rbp-70h]
  __int128 v91; // [rsp+128h] [rbp-60h]
  int v92; // [rsp+138h] [rbp-50h]

  v7 = a4;
  v8 = a3;
  v81 = a2;
  v88 = a1;
  *(_QWORD *)&Size[1] = a5;
  v11 = a6;
  v72 = a6;
  DeleteCount = 0;
  MatchData = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  RestartKey = 0;
  v63 = 0;
  Size[0] = 0;
  v12 = *(_QWORD **)(a3 + 24);
  v74 = a4;
  v65 = (_QWORD *)(*(_QWORD *)(v12[23] + 320LL) + 280LL);
  v13 = 0;
  v76 = 0;
  v82 = 0;
  v80 = NtfsMapUserBuffer(a2, 1073741840);
  if ( *(_QWORD *)(a2 + 8) )
    v62 = 0;
  else
    v62 = *(_BYTE *)(a2 + 64);
  if ( (*(_DWORD *)(v12[66] + 24LL) & 0x1000) != 0 )
    TxfDoPublishCommittedChangesToDefaultReaderSectionWithTryExcept(a1, v12, a7);
  if ( !a7 )
    v8 = v12[35];
  while ( 1 )
  {
    v15 = v7[14];
    if ( v15 )
    {
      v16 = 0;
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v15 + 528) + 64LL) + 136LL), 1u);
      if ( v15 == v7[14] )
      {
        TxfIncrementBackupAttributeDependencies(v15);
        v8 = v7[15];
        v16 = 1;
      }
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v15 + 528) + 64LL) + 136LL));
      if ( v16 )
        break;
    }
    v7 = (_QWORD *)v7[5];
    if ( !v7 )
      goto LABEL_15;
  }
  a7 = 0;
  v82 = v7;
LABEL_15:
  v17 = *(_QWORD *)(v8 + 24);
  v79 = v17;
  v87 = v17;
  v18 = v74;
  v19 = *(_QWORD *)(v74[33] + 16LL);
  v20 = **(_QWORD **)&Size[1];
  if ( **(_QWORD **)&Size[1] >= v19 )
  {
    v58 = a6;
    v57 = 0;
    goto LABEL_97;
  }
  if ( v20 + a6 > v19 )
  {
    Size[0] = v20 + a6 - v19;
    v11 = v19 - v20;
    v72 = v19 - v20;
  }
  if ( a7 )
    goto LABEL_49;
  v63 = v20;
  v21 = v11;
  v64 = v11;
  v22 = v20;
  do
  {
    v23 = *(_QWORD *)(v17 + 32);
    if ( v22 + v21 > v23 )
    {
      if ( v22 >= v23 )
        goto LABEL_49;
      v21 = v23 - v20;
      v64 = v23 - v20;
    }
    *(_QWORD *)&MatchData = v22 >> 12;
    DWORD2(v90) = ((v22 & 0xFFF) + 4095 + v21) >> 12;
    RestartKey = 0;
    ExAcquireFastMutex((PFAST_MUTEX)v18[32]);
    if ( (v18[1] & 0x800) != 0 )
      v24 = 0;
    else
      v24 = (unsigned int *)RtlEnumerateGenericTableLikeADirectory(
                              (PRTL_AVL_TABLE)(v18 + 19),
                              TxfMatchPageRange,
                              &MatchData,
                              0,
                              &RestartKey,
                              &DeleteCount,
                              &MatchData);
    ExReleaseFastMutex((PFAST_MUTEX)v18[32]);
    if ( !v24 )
    {
      v28 = v21;
LABEL_32:
      v29 = v79;
      v30 = *(struct _ERESOURCE **)(*(_QWORD *)(v79 + 184) + 112LL);
      if ( v30 && !ExIsResourceAcquiredSharedLite(v30) )
      {
        LOBYTE(v31) = 1;
        NtfsAcquirePagingResourceExclusive(a1, *(_QWORD *)(v29 + 184), v31);
        v13 = v29;
        v76 = v29;
      }
      v32 = (NTSTATUS *)(v81 + 48);
      LOBYTE(v25) = 1;
      CcCopyReadEx(
        v8,
        &v63,
        v28,
        v25,
        v80 + (unsigned int)(v63 - **(_DWORD **)&Size[1]),
        v81 + 48,
        *(_QWORD *)(v81 + 152));
      v36 = (unsigned int)*v32;
      if ( (int)v36 < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)v36 < 0xFFFFFFED
          && (_DWORD)v36 != -1073741802
          && (_DWORD)v36 != -1073741807
          && (unsigned int)(v36 + 2147483643) > 1
          && (_DWORD)v36 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v36, 3413296);
        }
        ExRaiseStatus(*v32);
      }
      if ( v13 )
      {
        NtfsReleasePagingResourcePriv(v33, *(_QWORD *)(v13 + 184), v34, v35);
        v13 = 0;
        v76 = 0;
      }
      v20 = v63 + v28;
      v63 = v20;
      v21 -= v28;
      goto LABEL_47;
    }
    v26 = *(_QWORD *)v24;
    if ( *(_QWORD *)v24 > (unsigned __int64)MatchData )
    {
      v28 = ((_DWORD)v26 << 12) - v63;
      goto LABEL_32;
    }
    v27 = v24[6];
    if ( v27 + v26 >= (unsigned __int64)MatchData + DWORD2(v90) )
      break;
    v20 = (v27 + v26) << 12;
    v63 = v20;
    v21 = v11 + **(_DWORD **)&Size[1] - (((_DWORD)v26 + (_DWORD)v27) << 12);
LABEL_47:
    v64 = v21;
    v22 = v20;
    v17 = v79;
    v18 = v74;
  }
  while ( v21 );
  v18 = v74;
LABEL_49:
  v37 = **(_QWORD **)&Size[1];
  v63 = **(_QWORD **)&Size[1];
  v64 = v11;
  do
  {
    if ( ((v37 ^ (v11 + v37 - 1)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
      v38 = 0x40000 - (v63 & 0x3FFFF);
    else
      v38 = v11;
    v77 = 0;
    v39 = v18;
    do
    {
      *(_QWORD *)&MatchData = v63 >> 12;
      v40 = v38;
      DWORD2(v90) = (v38 + (v63 & 0xFFF) + 4095) >> 12;
      RestartKey = 0;
      ExAcquireFastMutex((PFAST_MUTEX)v39[32]);
      for ( i = 0; (v39[1] & 0x800) == 0; i = 1 )
      {
        v78 = RtlEnumerateGenericTableLikeADirectory(
                (PRTL_AVL_TABLE)(v39 + 19),
                TxfMatchPageRange,
                &MatchData,
                i,
                &RestartKey,
                &DeleteCount,
                &MatchData);
        if ( !v78 )
          break;
        ExReleaseFastMutex((PFAST_MUTEX)v39[32]);
        v42 = v78;
        v43 = *v78 << 12;
        v71 = v43;
        v44 = *((_DWORD *)v78 + 6) << 12;
        v66 = v44;
        if ( v63 <= v43 )
        {
          v46 = v43;
          v45 = v44;
        }
        else
        {
          v45 = v43 - v63 + v44;
          v44 = v45;
          v66 = v45;
          v43 = v63;
          v71 = v63;
          v46 = v63;
        }
        if ( v40 + v63 < v46 + v45 )
        {
          v44 = v63 - v46 + v38;
          v66 = v44;
          v45 = v44;
        }
        do
        {
          v83 = 0;
          v47 = 4096 - (v43 & 0xFFF);
          LODWORD(v68) = v47;
          if ( v47 > v45 )
            v47 = v44;
          LODWORD(v71) = v47;
          LODWORD(v68) = v47;
          v86 = 1LL << ((v46 >> 12) & 0x3F);
          if ( (v86 & v77) == 0 )
          {
            v68 = v80 + (unsigned int)(v43 - **(_DWORD **)&Size[1]);
            v48 = v46 - ((unsigned int)*v42 << 12);
            v85 = v48;
            v84 = v48;
            v83 = v48 + (v42[1] << 12);
            v49 = v65;
            v61 = NtfsAcquireScbPagingResourceShared(a1, *v65);
            if ( a1 )
            {
              v69 = 0;
              for ( j = 0; ; j = (unsigned int)(j + 1) )
              {
                v69 = j;
                if ( (unsigned int)j >= 2 )
                  break;
                v52 = *(_QWORD *)(a1 + 8 * j + 48);
                if ( !v52 || v52 == *(_QWORD *)(*v49 + 184LL) )
                {
                  *(_QWORD *)(a1 + 8LL * (unsigned int)j + 48) = *(_QWORD *)(*v49 + 184LL);
                  break;
                }
              }
            }
            v53 = (NTSTATUS *)(v81 + 48);
            LOBYTE(v50) = 1;
            CcCopyReadEx(*(_QWORD *)(*v65 + 280LL), &v83, (unsigned int)v71, v50, v68, v81 + 48, *(_QWORD *)(v81 + 152));
            v54 = (unsigned int)*v53;
            if ( (int)v54 < 0 )
            {
              if ( NtfsStatusDebugFlags
                && (unsigned int)v54 < 0xFFFFFFED
                && (_DWORD)v54 != -1073741802
                && (_DWORD)v54 != -1073741807
                && (unsigned int)(v54 + 2147483643) > 1
                && (_DWORD)v54 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(a1, v54, 3413650);
              }
              ExRaiseStatus(*v53);
            }
            if ( v61 )
            {
              if ( a1 )
              {
                v70 = 0;
                for ( k = 0; ; ++k )
                {
                  v70 = k;
                  if ( k >= 2 )
                    break;
                  if ( *(_QWORD *)(a1 + 8LL * k + 48) == *(_QWORD *)(*v65 + 184LL) )
                    *(_QWORD *)(a1 + 8LL * k + 48) = 0;
                }
              }
              ExReleaseResourceLite(*(PERESOURCE *)(*v65 + 16LL));
            }
            v56 = (_DWORD)v78 + 36 + 16 * ((unsigned int)v85 >> 12);
            v47 = v71;
            LOBYTE(v56) = v62;
            TxfReplaceDisplacedBytes(
              v68,
              v56,
              v85 & 0xFFFF0FFF,
              (unsigned __int16)v71,
              (__int64)&v78[2 * ((unsigned int)v85 >> 12) + 4] + 4);
            v77 |= v86;
            v42 = v78;
          }
          v43 += v47;
          v46 = v43;
          v71 = v43;
          v44 -= v47;
          v66 = v44;
          v45 = v44;
        }
        while ( v44 );
        DWORD2(v90) += MatchData - *(_DWORD *)v42;
        *(_QWORD *)&MatchData = *v42;
        ExAcquireFastMutex((PFAST_MUTEX)v39[32]);
        v40 = v38;
      }
      ExReleaseFastMutex((PFAST_MUTEX)v39[32]);
      if ( v39[14] )
        break;
      v39 = (_QWORD *)v39[5];
    }
    while ( v39 );
    v37 = v40 + v63;
    v63 += v40;
    v11 -= v38;
    v64 = v11;
    v18 = v74;
  }
  while ( v11 );
  v57 = v72;
  v13 = v76;
  v17 = v79;
  v58 = Size[0];
LABEL_97:
  v59 = v17 + 200;
  if ( (*(_DWORD *)(v17 + 200) & 0x400000) != 0 )
  {
    *(_QWORD *)(v17 + 504) = 0;
    ClearFlagInterlocked(v59, 0x400000);
  }
  if ( v13 )
    NtfsReleasePagingResourcePriv(v59, *(_QWORD *)(v13 + 184), v14, v17);
  if ( v82 )
    TxfDereferenceBackupAttributeForTxfVscb();
  if ( v58 )
    memset((void *)(v80 + v57), 0, v58);
  v60 = v81;
  *(_DWORD *)(v81 + 48) = 0;
  *(_QWORD *)(v60 + 56) = v57 + v58;
}

```

## disassembly

```asm
0x140285a00  mov     r11, rsp
0x140285a03  push    rbx
0x140285a04  push    rsi
0x140285a05  push    rdi
0x140285a06  push    r12
0x140285a08  push    r13
0x140285a0a  push    r14
0x140285a0c  push    r15
0x140285a0e  sub     rsp, 150h
0x140285a15  mov     rax, cs:__security_cookie
0x140285a1c  xor     rax, rsp
0x140285a1f  mov     [rsp+188h+var_48], rax
0x140285a27  mov     rbx, r9
0x140285a2a  mov     r15, r8
0x140285a2d  mov     rsi, rdx
0x140285a30  mov     [rsp+188h+var_C0], rdx
0x140285a38  mov     r14, rcx
0x140285a3b  mov     [rsp+188h+var_88], rcx
0x140285a43  mov     rax, [rsp+188h+arg_20]
0x140285a4b  mov     qword ptr [rsp+188h+Size+4], rax
0x140285a53  mov     r12d, [rsp+188h+arg_28]
0x140285a5b  mov     [r11-108h], r12d
0x140285a62  xor     edx, edx
0x140285a64  mov     [rsp+188h+var_124], edx
0x140285a68  xorps   xmm0, xmm0
0x140285a6b  xor     eax, eax
0x140285a6d  movups  xmmword ptr [r11-80h], xmm0
0x140285a72  movups  xmmword ptr [r11-70h], xmm0
0x140285a77  movups  xmmword ptr [r11-60h], xmm0
0x140285a7c  mov     [r11-50h], eax
0x140285a80  mov     [r11-0F0h], rdx
0x140285a87  mov     [rsp+188h+var_140], rdx
0x140285a8c  mov     dword ptr [rsp+188h+Size], edx
0x140285a93  mov     rdi, [r8+18h]
0x140285a97  mov     [r11-0F8h], rbx
0x140285a9e  mov     [rsp+188h+var_148], dl
0x140285aa2  mov     rax, [rdi+0B8h]
0x140285aa9  mov     rax, [rax+140h]
0x140285ab0  add     rax, 118h
0x140285ab6  mov     [rsp+188h+var_130], rax
0x140285abb  mov     r13d, edx
0x140285abe  mov     [r11-0E8h], rdx
0x140285ac5  mov     [rsp+188h+var_B8], rdx
0x140285acd  mov     edx, 40000010h
0x140285ad2  mov     rcx, rsi
0x140285ad5  call    NtfsMapUserBuffer
0x140285ada  mov     [rsp+188h+var_C8], rax
0x140285ae2  cmp     [rsi+8], r13
0x140285ae6  jnz     short loc_140285AF1
0x140285ae8  mov     dl, [rsi+40h]
0x140285aeb  mov     [rsp+188h+var_147], dl
0x140285aef  jmp     short loc_140285AF6
0x140285af1  mov     [rsp+188h+var_147], r13b
0x140285af6  mov     rax, [rdi+210h]
0x140285afd  test    dword ptr [rax+18h], 1000h
0x140285b04  jz      short loc_140285B19
0x140285b06  mov     r8d, [rsp+188h+arg_30]
0x140285b0e  mov     rdx, rdi
0x140285b11  mov     rcx, r14
0x140285b14  call    TxfDoPublishCommittedChangesToDefaultReaderSectionWithTryExcept
0x140285b19  cmp     [rsp+188h+arg_30], r13d
0x140285b21  jnz     short loc_140285B2A
0x140285b23  mov     r15, [rdi+118h]
0x140285b2a  mov     rdi, [rbx+70h]
0x140285b2e  test    rdi, rdi
0x140285b31  jz      short loc_140285B8E
0x140285b33  xor     sil, sil
0x140285b36  mov     rax, [rdi+210h]
0x140285b3d  mov     rcx, [rax+40h]
0x140285b41  mov     dl, 1; Wait
0x140285b43  mov     rcx, [rcx+88h]; Resource
0x140285b4a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140285b51  nop     dword ptr [rax+rax+00h]
0x140285b56  cmp     rdi, [rbx+70h]
0x140285b5a  jnz     short loc_140285B6B
0x140285b5c  mov     rcx, rdi
0x140285b5f  call    TxfIncrementBackupAttributeDependencies
0x140285b64  mov     r15, [rbx+78h]
0x140285b68  mov     sil, 1
0x140285b6b  mov     rax, [rdi+210h]
0x140285b72  mov     rcx, [rax+40h]
0x140285b76  mov     rcx, [rcx+88h]; Resource
0x140285b7d  call    cs:__imp_ExReleaseResourceLite
0x140285b84  nop     dword ptr [rax+rax+00h]
0x140285b89  test    sil, sil
0x140285b8c  jnz     short loc_140285B99
0x140285b8e  mov     rbx, [rbx+28h]
0x140285b92  test    rbx, rbx
0x140285b95  jnz     short loc_140285B2A
0x140285b97  jmp     short loc_140285BA9
0x140285b99  mov     [rsp+188h+arg_30], r13d
0x140285ba1  mov     [rsp+188h+var_B8], rbx
0x140285ba9  mov     r9, [r15+18h]
0x140285bad  mov     [rsp+188h+var_D0], r9
0x140285bb5  mov     [rsp+188h+var_90], r9
0x140285bbd  mov     rdi, [rsp+188h+var_F8]
0x140285bc5  mov     rax, [rdi+108h]
0x140285bcc  mov     rdx, [rax+10h]
0x140285bd0  mov     rax, qword ptr [rsp+188h+Size+4]
0x140285bd8  mov     rcx, [rax]
0x140285bdb  cmp     rcx, rdx
0x140285bde  jge     loc_14028636A
0x140285be4  lea     r8, [rcx+r12]
0x140285be8  cmp     r8, rdx
0x140285beb  jle     short loc_140285C04
0x140285bed  mov     eax, r8d
0x140285bf0  sub     eax, edx
0x140285bf2  mov     dword ptr [rsp+188h+Size], eax
0x140285bf9  sub     r12d, eax
0x140285bfc  mov     [rsp+188h+var_108], r12d
0x140285c04  mov     r10d, 0FFFh
0x140285c0a  cmp     [rsp+188h+arg_30], 0
0x140285c12  jnz     loc_140285EAB
0x140285c18  mov     [rsp+188h+var_140], rcx
0x140285c1d  mov     ebx, r12d
0x140285c20  mov     [rsp+188h+var_138], ebx
0x140285c24  mov     rdx, rcx
0x140285c27  mov     r8, [r9+20h]
0x140285c2b  mov     eax, ebx
0x140285c2d  add     rax, rdx
0x140285c30  cmp     rax, r8
0x140285c33  jbe     short loc_140285C47
0x140285c35  cmp     rdx, r8
0x140285c38  jnb     loc_140285EAB
0x140285c3e  mov     ebx, r8d
0x140285c41  sub     ebx, ecx
0x140285c43  mov     [rsp+188h+var_138], ebx
0x140285c47  mov     rax, rdx
0x140285c4a  shr     rax, 0Ch
0x140285c4e  mov     qword ptr [rsp+188h+MatchData], rax
0x140285c56  and     rdx, r10
0x140285c59  mov     ecx, ebx
0x140285c5b  add     rdx, 0FFFh
0x140285c62  add     rcx, rdx
0x140285c65  shr     rcx, 0Ch
0x140285c69  mov     [rsp+188h+var_68], ecx
0x140285c70  mov     [rsp+188h+var_F0], 0
0x140285c7c  mov     rcx, [rdi+100h]; FastMutex
0x140285c83  call    cs:__imp_ExAcquireFastMutex
0x140285c8a  nop     dword ptr [rax+rax+00h]
0x140285c8f  test    dword ptr [rdi+8], 800h
0x140285c96  jnz     short loc_140285CE6
0x140285c98  lea     rcx, [rdi+98h]; Table
0x140285c9f  lea     rax, [rsp+188h+MatchData]
0x140285ca7  mov     [rsp+188h+Buffer], rax; Buffer
0x140285cac  lea     rax, [rsp+188h+var_124]
0x140285cb1  mov     [rsp+188h+DeleteCount], rax; DeleteCount
0x140285cb6  lea     rax, [rsp+188h+var_F0]
0x140285cbe  mov     [rsp+188h+RestartKey], rax; RestartKey
0x140285cc3  xor     r9d, r9d; NextFlag
0x140285cc6  lea     r8, [rsp+188h+MatchData]; MatchData
0x140285cce  lea     rdx, TxfMatchPageRange; MatchFunction
0x140285cd5  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x140285cdc  nop     dword ptr [rax+rax+00h]
0x140285ce1  mov     rsi, rax
0x140285ce4  jmp     short loc_140285CE8
0x140285ce6  xor     esi, esi
0x140285ce8  mov     rcx, [rdi+100h]; FastMutex
0x140285cef  call    cs:__imp_ExReleaseFastMutex
0x140285cf6  nop     dword ptr [rax+rax+00h]
0x140285cfb  test    rsi, rsi
0x140285cfe  jz      short loc_140285D58
0x140285d00  mov     rdi, [rsi]
0x140285d03  cmp     rdi, qword ptr [rsp+188h+MatchData]
0x140285d0b  ja      short loc_140285D4F
0x140285d0d  mov     edx, [rsi+18h]
0x140285d10  lea     rcx, [rdx+rdi]
0x140285d14  mov     eax, [rsp+188h+var_68]
0x140285d1b  add     rax, qword ptr [rsp+188h+MatchData]
0x140285d23  cmp     rcx, rax
0x140285d26  jnb     loc_140285E9D
0x140285d2c  shl     rcx, 0Ch
0x140285d30  mov     [rsp+188h+var_140], rcx
0x140285d35  lea     eax, [rdi+rdx]
0x140285d38  shl     eax, 0Ch
0x140285d3b  mov     rdx, qword ptr [rsp+188h+Size+4]
0x140285d43  mov     ebx, [rdx]
0x140285d45  sub     ebx, eax
0x140285d47  add     ebx, r12d
0x140285d4a  jmp     loc_140285E76
0x140285d4f  shl     edi, 0Ch
0x140285d52  sub     edi, dword ptr [rsp+188h+var_140]
0x140285d56  jmp     short loc_140285D5A
0x140285d58  mov     edi, ebx
0x140285d5a  test    r13, r13
0x140285d5d  jnz     short loc_140285DA4
0x140285d5f  mov     rsi, [rsp+188h+var_D0]
0x140285d67  mov     rax, [rsi+0B8h]
0x140285d6e  mov     rcx, [rax+70h]; Resource
0x140285d72  test    rcx, rcx
0x140285d75  jz      short loc_140285DA4
0x140285d77  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140285d7e  nop     dword ptr [rax+rax+00h]
0x140285d83  test    eax, eax
0x140285d85  jnz     short loc_140285DA4
0x140285d87  mov     r8b, 1
0x140285d8a  mov     rdx, [rsi+0B8h]
0x140285d91  mov     rcx, r14
0x140285d94  call    NtfsAcquirePagingResourceExclusive
0x140285d99  mov     r13, rsi
0x140285d9c  mov     [rsp+188h+var_E8], rsi
0x140285da4  mov     rdx, [rsp+188h+var_C0]
0x140285dac  lea     rsi, [rdx+30h]
0x140285db0  mov     eax, dword ptr [rsp+188h+var_140]
0x140285db4  mov     rcx, qword ptr [rsp+188h+Size+4]
0x140285dbc  sub     eax, [rcx]
0x140285dbe  mov     ecx, eax
0x140285dc0  add     rcx, [rsp+188h+var_C8]
0x140285dc8  mov     rax, [rdx+98h]
0x140285dcf  mov     [rsp+188h+Buffer], rax
0x140285dd4  mov     [rsp+188h+DeleteCount], rsi
0x140285dd9  mov     [rsp+188h+RestartKey], rcx
0x140285dde  mov     r9b, 1
0x140285de1  mov     r8d, edi
0x140285de4  lea     rdx, [rsp+188h+var_140]
0x140285de9  mov     rcx, r15
0x140285dec  call    cs:__imp_CcCopyReadEx
0x140285df3  nop     dword ptr [rax+rax+00h]
0x140285df8  mov     edx, [rsi]
0x140285dfa  test    edx, edx
0x140285dfc  jns     short loc_140285E4C
0x140285dfe  mov     al, cs:NtfsStatusDebugFlags
0x140285e04  test    al, al
0x140285e06  jz      short loc_140285E3E
0x140285e08  cmp     edx, 0FFFFFFEDh
0x140285e0b  jnb     short loc_140285E3E
0x140285e0d  cmp     edx, 0C0000016h
0x140285e13  jz      short loc_140285E3E
0x140285e15  cmp     edx, 0C0000011h
0x140285e1b  jz      short loc_140285E3E
0x140285e1d  lea     eax, [rdx+7FFFFFFBh]
0x140285e23  cmp     eax, 1
0x140285e26  jbe     short loc_140285E3E
0x140285e28  cmp     edx, 0C00000D8h
0x140285e2e  jz      short loc_140285E3E
0x140285e30  mov     r8d, 341530h
0x140285e36  mov     rcx, r14
0x140285e39  call    NtfsStatusTraceAndDebugInternal
0x140285e3e  mov     ecx, [rsi]; Status
0x140285e40  call    cs:__imp_ExRaiseStatus
0x140285e4c  test    r13, r13
0x140285e4f  jz      short loc_140285E68
0x140285e51  mov     rdx, [r13+0B8h]
0x140285e58  call    NtfsReleasePagingResourcePriv
0x140285e5d  xor     r13d, r13d
0x140285e60  mov     [rsp+188h+var_E8], r13
0x140285e68  mov     ecx, edi
0x140285e6a  add     rcx, [rsp+188h+var_140]
0x140285e6f  mov     [rsp+188h+var_140], rcx
0x140285e74  sub     ebx, edi
0x140285e76  mov     [rsp+188h+var_138], ebx
0x140285e7a  mov     rdx, rcx
0x140285e7d  test    ebx, ebx
0x140285e7f  mov     r9, [rsp+188h+var_D0]
0x140285e87  mov     r10d, 0FFFh
0x140285e8d  mov     rdi, [rsp+188h+var_F8]
0x140285e95  jnz     loc_140285C27
0x140285e9b  jmp     short loc_140285EA3
0x140285e9d  mov     r10d, 0FFFh
0x140285ea3  mov     rdi, [rsp+188h+var_F8]
0x140285eab  mov     rax, qword ptr [rsp+188h+Size+4]
0x140285eb3  mov     rdx, [rax]
0x140285eb6  mov     [rsp+188h+var_140], rdx
0x140285ebb  mov     [rsp+188h+var_138], r12d
0x140285ec0  mov     eax, r12d
0x140285ec3  lea     rcx, [rdx-1]
0x140285ec7  add     rcx, rax
0x140285eca  xor     rcx, rdx
0x140285ecd  test    rcx, 0FFFFFFFFFFFC0000h
0x140285ed4  jz      short loc_140285EEA
0x140285ed6  mov     eax, dword ptr [rsp+188h+var_140]
0x140285eda  and     eax, 3FFFFh
0x140285edf  mov     r13d, 40000h
0x140285ee5  sub     r13d, eax
0x140285ee8  jmp     short loc_140285EED
0x140285eea  mov     r13d, r12d
0x140285eed  mov     [rsp+188h+var_E0], 0
0x140285ef9  mov     rbx, rdi
0x140285efc  mov     rcx, [rsp+188h+var_140]
0x140285f01  mov     rax, rcx
0x140285f04  shr     rax, 0Ch
0x140285f08  mov     qword ptr [rsp+188h+MatchData], rax
0x140285f10  mov     esi, r13d
0x140285f13  and     rcx, r10
0x140285f16  lea     rax, [rcx+0FFFh]
0x140285f1d  add     rax, rsi
0x140285f20  shr     rax, 0Ch
0x140285f24  mov     [rsp+188h+var_68], eax
0x140285f2b  mov     [rsp+188h+var_F0], 0
0x140285f37  mov     rcx, [rbx+100h]; FastMutex
0x140285f3e  call    cs:__imp_ExAcquireFastMutex
0x140285f45  nop     dword ptr [rax+rax+00h]
0x140285f4a  xor     r9d, r9d; NextFlag
0x140285f4d  test    dword ptr [rbx+8], 800h
0x140285f54  jnz     loc_1402862F4
0x140285f5a  lea     rcx, [rbx+98h]; Table
0x140285f61  lea     rax, [rsp+188h+MatchData]
0x140285f69  mov     [rsp+188h+Buffer], rax; Buffer
0x140285f6e  lea     rax, [rsp+188h+var_124]
0x140285f73  mov     [rsp+188h+DeleteCount], rax; DeleteCount
  ... truncated ...
```
