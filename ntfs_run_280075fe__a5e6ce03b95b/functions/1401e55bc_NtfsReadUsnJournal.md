# NtfsReadUsnJournal

- ea: `0x1401e55bc`
- end: `0x1401e697b`
- name: `NtfsReadUsnJournal`
- size: `5055`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1401e52d0`
- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x1400085e0`
- `0x140009830`
- `0x14000c290`
- `0x140020de0`
- `0x140025830`
- `0x14002b4a0`
- `0x140041d28`
- `0x140048a74`
- `0x140059250`
- `0x1400592c0`
- `0x1400596c0`
- `0x1400bdc7c`
- `0x1400bdd90`
- `0x1400bde74`
- `0x1400bdebc`
- `0x1400bdf00`
- `0x1401aab20`
- `0x1401e55bc`
- `0x1401e6984`
- `0x1401e6c80`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x1401e5c13`
- `ntoskrnl!CcMapData` at `0x1401e5c13`
- `ntoskrnl!ProbeForWrite` at `0x1401e6297`
- `ntoskrnl!ProbeForWrite` at `0x1401e6297`
- `ntoskrnl!ProbeForRead` at `0x1401e626c`
- `ntoskrnl!ProbeForRead` at `0x1401e626c`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e60f0`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e60f0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e59fc`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e59fc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401e651e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401e651e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e60dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e60dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401e5950`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401e5950`
- `ntoskrnl!CcUnpinData` at `0x1401e5fb5`
- `ntoskrnl!CcUnpinData` at `0x1401e6931`
- `ntoskrnl!CcUnpinData` at `0x1402b10f3`
- `ntoskrnl!CcUnpinData` at `0x1401e5fb5`
- `ntoskrnl!CcUnpinData` at `0x1401e6931`
- `ntoskrnl!CcUnpinData` at `0x1402b10f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e5aa8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e6899`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b1136`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e5aa8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e6899`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b1136`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5858`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5b21`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5858`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5b21`
- `ntoskrnl!ExRaiseStatus` at `0x1401e66a8`
- `ntoskrnl!ExRaiseStatus` at `0x1401e66a8`

## pseudocode

```c
__int64 __fastcall NtfsReadUsnJournal(__int64 a1, __int64 a2, char a3, __int64 a4)
{
  char v4; // r10
  __int64 v7; // r15
  __int64 v8; // rdx
  __int64 v9; // rcx
  union _LARGE_INTEGER *v10; // r8
  __int64 v11; // rcx
  union _LARGE_INTEGER v12; // r14
  int v13; // eax
  int v14; // edi
  unsigned int v15; // edi
  __int64 v16; // rsi
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // eax
  char v20; // bl
  void *v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rdx
  bool v26; // sf
  __int64 v27; // rbx
  _QWORD *PoolWithTag; // r14
  __int64 v29; // rax
  _QWORD *v30; // rdx
  struct _ERESOURCE *v31; // rcx
  int v32; // r9d
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rbx
  unsigned __int16 *v37; // rbx
  unsigned __int16 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rcx
  unsigned int v41; // eax
  unsigned __int16 v42; // cx
  unsigned int v43; // r14d
  int v44; // eax
  size_t v45; // r8
  char *v46; // rdx
  char *v47; // rbx
  void *v48; // rcx
  bool v49; // zf
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // rax
  __int16 UShortFromUser; // ax
  unsigned __int16 v54; // ax
  __int64 v55; // r8
  int v56; // r14d
  __int64 v57; // rax
  char *v58; // rax
  _WORD *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rdx
  struct _ERESOURCE *v64; // rcx
  __int16 v65; // si
  __int64 v66; // r9
  __int64 v67; // r10
  unsigned __int16 v68; // ax
  int Bcb; // [rsp+20h] [rbp-1C8h]
  int Buffer; // [rsp+28h] [rbp-1C0h]
  char v71; // [rsp+71h] [rbp-177h]
  char v72; // [rsp+72h] [rbp-176h]
  char v73; // [rsp+73h] [rbp-175h]
  char v74; // [rsp+74h] [rbp-174h]
  char v75; // [rsp+75h] [rbp-173h]
  bool v76; // [rsp+7Ch] [rbp-16Ch]
  char v77[3]; // [rsp+7Dh] [rbp-16Bh] BYREF
  unsigned int v78; // [rsp+80h] [rbp-168h]
  int v79; // [rsp+84h] [rbp-164h]
  void *v80; // [rsp+88h] [rbp-160h]
  PVOID Src; // [rsp+90h] [rbp-158h] BYREF
  unsigned int v82; // [rsp+98h] [rbp-150h]
  __int64 v83; // [rsp+A0h] [rbp-148h]
  __int64 v84; // [rsp+A8h] [rbp-140h]
  union _LARGE_INTEGER FileOffset; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v86; // [rsp+B8h] [rbp-130h]
  __int64 v87; // [rsp+C0h] [rbp-128h]
  _QWORD *v88; // [rsp+C8h] [rbp-120h]
  __int64 v89; // [rsp+D0h] [rbp-118h]
  int v90; // [rsp+D8h] [rbp-110h]
  int v91; // [rsp+DCh] [rbp-10Ch]
  union _LARGE_INTEGER v92; // [rsp+E0h] [rbp-108h]
  __int64 v93; // [rsp+E8h] [rbp-100h] BYREF
  union _LARGE_INTEGER v94; // [rsp+F0h] [rbp-F8h]
  __int64 v95; // [rsp+F8h] [rbp-F0h]
  __int64 v96; // [rsp+100h] [rbp-E8h]
  __int128 v97; // [rsp+108h] [rbp-E0h]
  PVOID v98[2]; // [rsp+118h] [rbp-D0h] BYREF
  __int128 v99; // [rsp+128h] [rbp-C0h] BYREF
  __int128 v100; // [rsp+138h] [rbp-B0h] BYREF
  __int128 v101; // [rsp+148h] [rbp-A0h]
  _QWORD v102[10]; // [rsp+160h] [rbp-88h] BYREF

  v4 = a4;
  v72 = a4;
  v7 = a1;
  v95 = a1;
  Src = 0;
  v97 = 0;
  *(_OWORD *)v98 = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  v8 = *(_QWORD *)(a2 + 184);
  v83 = v8;
  v9 = *(_QWORD *)(v8 + 48);
  v10 = *(union _LARGE_INTEGER **)(v9 + 24);
  if ( v10 )
  {
    v11 = *(_QWORD *)(v9 + 32);
    v12 = v10[24];
    v92 = v12;
    v13 = *(_DWORD *)(v12.QuadPart + 4);
    if ( (v13 & 1) == 0 )
    {
      if ( !v11 || *(_BYTE *)(v11 + 88) != 4 || (a4 = 2, (v13 & 2) == 0) )
      {
        NtfsRaiseStatusInternal(v7, -1073741202, 0, 0, 0);
        __debugbreak();
      }
    }
    v94 = v12;
    FileOffset = v10[23];
    if ( v11 )
      v14 = *(unsigned __int8 *)(v11 + 88);
    else
      v14 = 5;
  }
  else
  {
    v12.QuadPart = 0;
    v92.QuadPart = 0;
    v94.QuadPart = 0;
    v11 = 0;
    FileOffset.QuadPart = 0;
    v14 = 1;
  }
  if ( !v4
    && (!v11 || !_bittest16((const signed __int16 *)(v11 + 104), 9u) && (*(_BYTE *)(a2 + 64) || *(_BYTE *)(v8 + 1) != 4)) )
  {
    if ( (!v7 || (*(_DWORD *)(v7 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      if ( v11 )
        v65 = *(_WORD *)(v11 + 104);
      else
        LOBYTE(v65) = 0;
      v66 = v11 + 16;
      if ( !v11 )
        v66 = 0;
      v67 = *(_QWORD *)(v12.QuadPart + 248);
      v68 = *(_WORD *)(v67 + 6);
      if ( v68 > 0x40u || (v68 & 1) != 0 )
        v68 = 0;
      McTemplateU0pdpwwpiwd_EtwWriteTransfer(
        v10[23].QuadPart,
        (unsigned int)usnsup_c334,
        (unsigned int)KeGetCurrentThread(),
        v14,
        v12.QuadPart,
        *(_WORD *)(v12.QuadPart + 7872) >> 1,
        *(_QWORD *)(v12.QuadPart + 7880),
        v68 >> 1,
        v67 + 32,
        FileOffset.QuadPart,
        *(_QWORD *)(v10[23].QuadPart + 8),
        *(_WORD *)v66 >> 1,
        *(_QWORD *)(v66 + 8),
        v65);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v7, 3221225506LL, 2818399);
    LOBYTE(a4) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(v7, a2, 3221225506LL, a4, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225506LL, 2818400);
    return 3221225506LL;
  }
  v15 = 0;
  v16 = 0;
  v84 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  DWORD2(v101) = 131074;
  v76 = 1;
  if ( a3 )
    v76 = (*(_BYTE *)(v7 + 12) & 1) != 0;
  v18 = NtfsMapUserBuffer(a2, 16);
  v88 = (_QWORD *)v18;
  if ( *(_QWORD *)(a2 + 8) )
    v71 = 0;
  else
    v71 = *(_BYTE *)(a2 + 64);
  v19 = *(_DWORD *)(v7 + 12);
  v90 = (v19 & 1) == 0;
  v91 = v90;
  *(_DWORD *)(v7 + 12) = v19 | 1;
  if ( *(_BYTE *)(a2 + 64) )
  {
    if ( a3 )
    {
      ProbeForRead(*(volatile void **)(v83 + 32), *(unsigned int *)(v83 + 16), 4u);
      v18 = (__int64)v88;
    }
    if ( !*(_QWORD *)(a2 + 8) )
      ProbeForWrite((volatile void *)v18, *(unsigned int *)(v83 + 8), 4u);
  }
  else if ( *(_QWORD *)(v83 + 32) != ((*(_QWORD *)(v83 + 32) + 3LL) & 0xFFFFFFFFFFFFFFFCuLL)
         || !*(_QWORD *)(a2 + 8) && v18 != ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    v15 = -1073741811;
    if ( NtfsStatusDebugFlags )
    {
      v55 = 2818466;
      goto LABEL_102;
    }
    goto LABEL_188;
  }
  if ( !a3
    || (LOBYTE(v17) = 1,
        v75 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))NtfsAcquireSharedVcb)(
                v7,
                (union _LARGE_INTEGER)v12.QuadPart,
                v17),
        (*(_DWORD *)(v12.QuadPart + 4) & 0x80000) != 0) )
  {
    v16 = *(_QWORD *)(v12.QuadPart + 40);
  }
  else
  {
    v16 = 0;
  }
  v84 = v16;
  if ( (*(_DWORD *)(v12.QuadPart + 4) & 0x100000) == 0 && *(int *)(v12.QuadPart + 24) >= 0 )
  {
    if ( !v16 )
    {
      v15 = -1073741128;
      if ( NtfsStatusDebugFlags )
      {
        v55 = 2818512;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    if ( *(_DWORD *)(v83 + 16) < 0x28u )
    {
      v15 = -1073741592;
      if ( NtfsStatusDebugFlags )
      {
        v55 = 2818522;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    if ( a3 )
      v20 = *(_BYTE *)(a2 + 64);
    else
      v20 = 0;
    v21 = *(void **)(v83 + 32);
    if ( v20 )
      RtlCopyFromUser(&v99, v21, 0x28u);
    else
      RtlCopyVolatileMemory(&v99, v21, 0x28u);
    v22 = v83;
    if ( *(_DWORD *)(v83 + 16) >= 0x30u )
    {
      v52 = *(_QWORD *)(v83 + 32);
      v89 = v52;
      if ( v20 )
        UShortFromUser = RtlReadUShortFromUser(v52 + 40);
      else
        UShortFromUser = *(_WORD *)(v52 + 40);
      WORD4(v101) = UShortFromUser;
      if ( v20 )
        v54 = RtlReadUShortFromUser(v89 + 42);
      else
        v54 = *(_WORD *)(v89 + 42);
      WORD5(v101) = v54;
      if ( WORD4(v101) > v54 )
      {
        v15 = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v55 = 2818550;
          goto LABEL_102;
        }
        goto LABEL_188;
      }
      if ( WORD4(v101) > 3u || v54 < 2u )
      {
        v15 = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v55 = 2818560;
          goto LABEL_102;
        }
        goto LABEL_188;
      }
      v22 = v83;
    }
    if ( (_QWORD)v101 != *(_QWORD *)(v12.QuadPart + 1912) )
    {
      v15 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v55 = 2818581;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    v23 = *(_DWORD *)(v22 + 8);
    if ( v23 < 8 )
    {
      v15 = -1073741789;
      if ( NtfsStatusDebugFlags )
      {
        v55 = 2818592;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    v78 = v23 - 8;
    v80 = v88 + 1;
    v82 = 8;
    v24 = v16;
    if ( *(_WORD *)v16 != 1794 )
      v24 = *(_QWORD *)(v16 + 184);
    ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v24 + 104) + 64LL), 1u);
    v73 = 1;
    if ( v75 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))NtfsReleaseVcb)(v7, (union _LARGE_INTEGER)v12.QuadPart);
      v75 = 0;
    }
    if ( (*(_DWORD *)(v16 + 512) & 0x10000) != 0 )
    {
      v15 = -1073741202;
      if ( NtfsStatusDebugFlags )
      {
        v55 = 2818618;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    v25 = v99;
    v26 = (__int64)v99 < 0;
    if ( !(_QWORD)v99 )
    {
      v25 = *(_QWORD *)(v12.QuadPart + 1928);
      *(_QWORD *)&v99 = v25;
      v26 = v25 < 0;
    }
    if ( v26 || *((_QWORD *)&v100 + 1) > 0x7FFFFFFFFFFFFFFFuLL || v25 + *((_QWORD *)&v100 + 1) < 0 )
    {
      v15 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v55 = 2818640;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    while ( 1 )
    {
      if ( v25 < *(_QWORD *)(v12.QuadPart + 1928) )
      {
        *(_QWORD *)&v99 = *(_QWORD *)(v12.QuadPart + 1928);
        v15 = -1073741105;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221226191LL, 2818656);
        v25 = v99;
LABEL_130:
        *(_QWORD *)(a2 + 56) = v82;
        if ( v71 )
          RtlWriteULong64ToUser(v88, v25);
        else
          *v88 = v25;
        goto LABEL_188;
      }
      if ( v25 >= *(_QWORD *)(v16 + 32) )
      {
        if ( (*(_DWORD *)(v12.QuadPart + 4) & 0x2000000) != 0 )
        {
          v15 = -1073741662;
          if ( NtfsStatusDebugFlags )
          {
            v55 = 2818673;
            goto LABEL_102;
          }
          goto LABEL_188;
        }
        if ( !*((_QWORD *)&v100 + 1) )
          goto LABEL_130;
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 212));
        v74 = 1;
        if ( !v76 || a2 != *(_QWORD *)(v7 + 112) )
        {
          v27 = v99 + *((_QWORD *)&v100 + 1);
          v15 = 259;
          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, 0x78u, 0x7646744Eu);
          memset(PoolWithTag, 0, 0x48u);
          *(_OWORD *)(PoolWithTag + 9) = v99;
          *(_OWORD *)(PoolWithTag + 11) = v100;
          *(_OWORD *)(PoolWithTag + 13) = v101;
          v29 = v83;
          *(_QWORD *)(v83 + 32) = PoolWithTag + 9;
          *(_DWORD *)(v29 + 16) = 48;
          PoolWithTag[6] = a2;
          PoolWithTag[2] = v27;
          PoolWithTag[7] = v16;
          *((_DWORD *)PoolWithTag + 16) = 0;
          *((_DWORD *)PoolWithTag + 17) = 5;
          if ( v72 )
            *((_DWORD *)PoolWithTag + 17) = 7;
          if ( *(_QWORD *)(v7 + 112) == a2 )
            NtfsPrePostIrpInternal(v7, a2, 0, 0, 1);
          FsRtlAcquireHeaderMutex(v16 + 120, v16 + 160);
          if ( (unsigned __int8)NtfsSetCancelRoutine(a2, NtfsCancelReadUsnJournal, PoolWithTag, 1, Bcb) )
          {
            v30 = *(_QWORD **)(v16 + 600);
            if ( *v30 != v16 + 592 )
              __fastfail(3u);
            *PoolWithTag = v16 + 592;
            PoolWithTag[1] = v30;
            *v30 = PoolWithTag;
            *(_QWORD *)(v16 + 600) = PoolWithTag;
          }
          else
          {
            v15 = -1073741536;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221225760LL, 2884790);
            ExFreePoolWithTag(PoolWithTag, 0);
          }
          FsRtlReleaseHeaderMutex(v16 + 120, v16 + 160);
          if ( v15 == 259 )
            v74 = 0;
          goto LABEL_188;
        }
        if ( *(_WORD *)v16 == 1794 )
          v31 = (struct _ERESOURCE *)(*(_QWORD *)(v16 + 104) + 64LL);
        else
          v31 = *(struct _ERESOURCE **)(v16 + 8);
        ExReleaseResourceLite(v31);
        v73 = 0;
        LOBYTE(v32) = v72;
        v15 = NtOfsWaitForNewLength(
                v16,
                (int)v99 + DWORD2(v100),
                (unsigned __int64)&v100 & -(__int64)((_QWORD)v100 != 0),
                v32,
                a2,
                Buffer,
                (PLARGE_INTEGER)((unsigned __int64)&v100 & -(__int64)((_QWORD)v100 != 0)));
        if ( v15 )
          goto LABEL_188;
        v33 = v16;
        if ( *(_WORD *)v16 != 1794 )
          v33 = *(_QWORD *)(v16 + 184);
        ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v33 + 104) + 64LL), 1u);
        v73 = 1;
        _InterlockedDecrement((volatile signed __int32 *)(v16 + 212));
        v74 = 0;
        v34 = *(_QWORD *)(v16 + 192);
        if ( v16 != *(_QWORD *)(v34 + 40) )
        {
          if ( (*(_DWORD *)(v34 + 4) & 0x100000) != 0 || *(int *)(v12.QuadPart + 24) < 0 )
          {
            v15 = -1073741129;
            if ( NtfsStatusDebugFlags )
            {
              v55 = 2818784;
              goto LABEL_102;
            }
          }
          else
          {
            v15 = -1073741128;
            if ( NtfsStatusDebugFlags )
            {
              v55 = 2818786;
              goto LABEL_102;
            }
          }
          goto LABEL_188;
        }
        v25 = v99;
      }
LABEL_62:
      if ( !v78 )
        goto LABEL_130;
      v35 = *(_QWORD *)(v16 + 32);
      if ( v25 < v35 )
        break;
      if ( v82 != 8 )
        goto LABEL_130;
    }
    FileOffset.QuadPart = 0;
    v77[0] = 0;
    v93 = 0;
    v36 = v35 - v25;
    v86 = v36;
    if ( v36 > 0x40000 - ((unsigned int)v25 & 0x3FFFF) )
      v36 = 0x40000 - ((unsigned int)v25 & 0x3FFFF);
    v87 = v36;
    v86 = v36;
    FileOffset.QuadPart = v25 - *(_QWORD *)(v12.QuadPart + 1952);
    NtfsPerformPrefetch(*(PFILE_OBJECT *)(v16 + 280));
    CcMapData(*(PFILE_OBJECT *)(v16 + 280), &FileOffset, v36, 1u, &v98[1], &Src);
    *(union _LARGE_INTEGER *)&v97 = FileOffset;
    DWORD2(v97) = v36;
    LODWORD(v36) = (_DWORD)Src;
    v98[0] = Src;
    LODWORD(v25) = v99;
LABEL_67:
    if ( !(unsigned __int8)NtfsValidateUsnPage(
                             (unsigned int)v36 & 0xFFFFF000,
                             (unsigned int)v25 & 0xFFFFF000,
                             (unsigned int)&v99,
                             *(_QWORD *)(v16 + 32),
                             (__int64)v77,
                             (__int64)&v93) )
    {
      v15 = -1073741762;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_188;
      v55 = 2818869;
      goto LABEL_102;
    }
    if ( !v77[0] )
    {
      v15 = -1073741811;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_188;
      v55 = 2818879;
LABEL_102:
      NtfsStatusTraceAndDebugInternal(0, v15, v55);
      goto LABEL_188;
    }
    v37 = (unsigned __int16 *)Src;
    v38 = WORD5(v101);
    v25 = v99;
    v39 = v93;
    v96 = v93;
    v40 = v87;
    while ( 1 )
    {
      if ( v25 >= v39 )
      {
        if ( !v78 )
          goto LABEL_104;
        v57 = -(int)v39 & 0xFFF;
        if ( v57 > v40 )
          v57 = (unsigned int)v40;
        v36 = (__int64)v37 + v57;
        Src = (PVOID)v36;
        v25 += v57;
        *(_QWORD *)&v99 = v25;
        v87 = v40 - v57;
        v86 = v40 - v57;
        if ( v40 == v57 )
          goto LABEL_104;
        goto LABEL_67;
      }
      v79 = 0;
      v41 = *(_DWORD *)v37;
      LODWORD(v86) = *(_DWORD *)v37;
      v42 = v37[2];
      v18 = 2;
      if ( v38 >= 3u && v42 == 2 )
      {
        v56 = 76;
        v79 = 76;
        if ( !v72 )
        {
          v56 = v37[28] + 76;
          v79 = v56;
        }
        v43 = (v56 + 7) & 0xFFFFFFF8;
      }
      else
      {
        v43 = v41;
        v79 = v41;
        if ( v42 != 2 )
          goto LABEL_73;
        if ( v72 )
          v43 = 64;
      }
      v79 = v43;
LABEL_73:
      v44 = *((_DWORD *)v37 + 10);
      if ( (v44 & DWORD2(v99)) != 0 && (!HIDWORD(v99) || v44 < 0) && (unsigned __int16)(v42 - 2) <= 2u && v38 >= v42 )
      {
        if ( v43 > v78 )
        {
          v78 = 0;
LABEL_104:
          if ( v98[1] )
          {
            CcUnpinData(v98[1]);
            v98[1] = 0;
            v25 = v99;
          }
          v12 = v92;
          goto LABEL_62;
        }
        if ( v38 >= 3u && v42 == 2 )
        {
          memset(v102, 0, sizeof(v102));
          v102[0] = v43 | 0x300000000LL;
          v102[2] = 0;
          v102[1] = *((_QWORD *)v37 + 1);
          v102[4] = 0;
          v102[3] = *((_QWORD *)v37 + 2);
          *(_OWORD *)&v102[5] = *(_OWORD *)(v37 + 12);
          *(_OWORD *)&v102[7] = *(_OWORD *)(v37 + 20);
          LOWORD(v102[9]) = v37[28];
          WORD1(v102[9]) = 76;
          v45 = 80;
          v46 = (char *)v102;
          if ( v72 )
          {
            LOWORD(v102[9]) = 0;
            v49 = v71 == 0;
            v48 = v80;
          }
          else
          {
            v47 = (char *)v80;
            if ( v71 )
              RtlCopyToUser(v80, v102, 0x50u);
            else
              RtlCopyVolatileMemory(v80, v102, 0x50u);
            v45 = *((unsigned __int16 *)Src + 28);
            v46 = (char *)Src + 60;
            v48 = v47 + 76;
            v49 = v71 == 0;
          }
          if ( v49 )
            RtlCopyVolatileMemory(v48, v46, v45);
          else
            RtlCopyToUser(v48, v46, v45);
          v50 = v43;
LABEL_87:
          v37 = (unsigned __int16 *)Src;
        }
        else
        {
          v89 = v43;
          if ( v71 )
            RtlCopyToUser(v80, v37, v43);
          else
            RtlCopyVolatileMemory(v80, v37, v43);
          v50 = v43;
          v37 = (unsigned __int16 *)Src;
          if ( v72 && *((_WORD *)Src + 2) == 2 )
          {
            if ( v71 )
            {
              RtlWriteULongToUser(v80, v43);
              v58 = (char *)v80;
            }
            else
            {
              v58 = (char *)v80;
              *(_DWORD *)v80 = v43;
            }
            v59 = v58 + 56;
            if ( v71 )
              RtlWriteUShortToUser(v59, 0, v51);
            else
              *v59 = 0;
            v50 = v89;
            goto LABEL_87;
          }
        }
        v78 -= v43;
        v82 += v43;
        v80 = (char *)v80 + v50;
        v38 = WORD5(v101);
        v25 = v99;
      }
      v25 += (unsigned int)v86;
      *(_QWORD *)&v99 = v25;
      v37 = (unsigned __int16 *)((char *)v37 + (unsigned int)v86);
      Src = v37;
      v40 = v87 - (unsigned int)v86;
      v87 = v40;
      v86 = v40;
      v39 = v96;
    }
  }
  v15 = -1073741129;
  if ( NtfsStatusDebugFlags )
  {
    v55 = 2818502;
    goto LABEL_102;
  }
LABEL_188:
  if ( v98[1] )
  {
    CcUnpinData(v98[1]);
    v98[1] = 0;
  }
  if ( v73 )
  {
    if ( *(_WORD *)v16 == 1794 )
      v64 = (struct _ERESOURCE *)(*(_QWORD *)(v16 + 104) + 64LL);
    else
      v64 = *(struct _ERESOURCE **)(v16 + 8);
    ExReleaseResourceLite(v64);
  }
  if ( v74 )
    _InterlockedDecrement((volatile signed __int32 *)(v16 + 212));
  if ( v75 )
    ((void (__fastcall *)(_QWORD, _QWORD))NtfsReleaseVcb)(v7, (union _LARGE_INTEGER)v92.QuadPart);
  *(_DWORD *)(v7 + 12) &= ~v90;
  v60 = v7;
  if ( a2 != *(_QWORD *)(v7 + 112) )
    v60 = 0;
  if ( NtfsStatusDebugFlags
    && v15
    && v15 != 294
    && v15 - 298 > 1
    && v15 < 0xFFFFFFED
    && v15 != -1073741608
    && v15 != -1073741802
    && v15 != -1073741807
    && v15 + 2147483643 > 1
    && v15 != 259 )
  {
    NtfsStatusTraceAndDebugInternal(v60, v15, 2819146);
  }
  v61 = 0;
  if ( v15 != 259 )
    v61 = a2;
  v62 = 0;
  if ( v15 != 259 )
    v62 = a2;
  if ( a2 != *(_QWORD *)(v7 + 112) )
    v7 = 0;
  LOBYTE(v18) = v61 != 0;
  NtfsExtendedCompleteRequestInternal(v7, v62, v15, v18, (v15 & 0x80000000) == 0);
  return v15;
}

```

## disassembly

```asm
0x1401e55bc  mov     [rsp+arg_10], rbx
0x1401e55c1  push    rsi
0x1401e55c2  push    rdi
0x1401e55c3  push    r13
0x1401e55c5  push    r14
0x1401e55c7  push    r15
0x1401e55c9  sub     rsp, 1C0h
0x1401e55d0  mov     rax, cs:__security_cookie
0x1401e55d7  xor     rax, rsp
0x1401e55da  mov     [rsp+1E8h+var_38], rax
0x1401e55e2  mov     r10b, r9b
0x1401e55e5  mov     byte ptr [rsp+1E8h+var_176], r9b
0x1401e55ea  mov     bl, r8b
0x1401e55ed  mov     r13, rdx
0x1401e55f0  mov     r15, rcx
0x1401e55f3  mov     [rsp+1E8h+var_F0], rcx
0x1401e55fb  xor     r11d, r11d
0x1401e55fe  mov     [rsp+1E8h+Src], r11
0x1401e5606  xorps   xmm0, xmm0
0x1401e5609  movups  [rsp+1E8h+var_E0], xmm0
0x1401e5611  movups  xmmword ptr [rsp+1E8h+var_D0], xmm0
0x1401e5619  xorps   xmm1, xmm1
0x1401e561c  movups  [rsp+1E8h+var_C0], xmm1
0x1401e5624  movups  [rsp+1E8h+var_B0], xmm1
0x1401e562c  movups  [rsp+1E8h+var_A0], xmm1
0x1401e5634  mov     rdx, [rdx+0B8h]
0x1401e563b  mov     [rsp+1E8h+var_148], rdx
0x1401e5643  mov     rcx, [rdx+30h]
0x1401e5647  mov     r8, [rcx+18h]
0x1401e564b  test    r8, r8
0x1401e564e  jz      loc_1401E6909
0x1401e5654  mov     rcx, [rcx+20h]
0x1401e5658  mov     r14, [r8+0C0h]
0x1401e565f  mov     [rsp+1E8h+var_108], r14
0x1401e5667  mov     eax, [r14+4]
0x1401e566b  test    al, 1
0x1401e566d  jz      loc_1401E68D6
0x1401e5673  mov     [rsp+1E8h+var_F8], r14
0x1401e567b  mov     rax, [r8+0B8h]
0x1401e5682  mov     qword ptr [rsp+1E8h+FileOffset], rax
0x1401e568a  test    rcx, rcx
0x1401e568d  jz      loc_1401E68CC
0x1401e5693  movzx   edi, byte ptr [rcx+58h]
0x1401e5697  test    r10b, r10b
0x1401e569a  jz      loc_1401E6779
0x1401e56a0  mov     edi, r11d
0x1401e56a3  mov     rsi, r11
0x1401e56a6  mov     [rsp+1E8h+var_140], r11
0x1401e56ae  mov     byte ptr [rsp+1E8h+var_176+1], r11b
0x1401e56b3  mov     [rsp+1E8h+var_178], r11b
0x1401e56b8  mov     byte ptr [rsp+1E8h+var_176+2], r11b
0x1401e56bd  mov     byte ptr [rsp+1E8h+var_176+3], r11b
0x1401e56c2  mov     dword ptr [rsp+1E8h+var_A0+8], 20002h
0x1401e56cd  mov     cl, 1
0x1401e56cf  mov     [rsp+1E8h+var_16C], cl
0x1401e56d3  test    bl, bl
0x1401e56d5  jnz     loc_1401E68B7
0x1401e56db  mov     edx, 10h
0x1401e56e0  mov     rcx, r13
0x1401e56e3  call    NtfsMapUserBuffer
0x1401e56e8  mov     r9, rax
0x1401e56eb  mov     [rsp+1E8h+var_120], rax
0x1401e56f3  cmp     [r13+8], rsi
0x1401e56f7  jz      loc_1401E68AA
0x1401e56fd  mov     [rsp+1E8h+var_177], sil
0x1401e5702  mov     eax, [r15+0Ch]
0x1401e5706  mov     ecx, eax
0x1401e5708  not     ecx
0x1401e570a  and     ecx, 1
0x1401e570d  mov     [rsp+1E8h+var_110], ecx
0x1401e5714  mov     [rsp+1E8h+var_10C], ecx
0x1401e571b  or      eax, 1
0x1401e571e  mov     [r15+0Ch], eax
0x1401e5722  mov     [rsp+1E8h+var_178], 1
0x1401e5727  cmp     byte ptr [r13+40h], 0
0x1401e572c  jnz     loc_1401E6253
0x1401e5732  mov     rcx, [rsp+1E8h+var_148]
0x1401e573a  mov     rcx, [rcx+20h]
0x1401e573e  lea     rax, [rcx+3]
0x1401e5742  and     rax, 0FFFFFFFFFFFFFFFCh
0x1401e5746  cmp     rcx, rax
0x1401e5749  jnz     loc_1401E5A70
0x1401e574f  cmp     qword ptr [r13+8], 0
0x1401e5754  jz      loc_1401E5A5F
0x1401e575a  mov     [rsp+1E8h+var_178], 0
0x1401e575f  test    bl, bl
0x1401e5761  jnz     loc_1401E6037
0x1401e5767  mov     rsi, [r14+28h]
0x1401e576b  mov     [rsp+1E8h+var_140], rsi
0x1401e5773  test    dword ptr [r14+4], 100000h
0x1401e577b  jnz     loc_1401E6457
0x1401e5781  cmp     dword ptr [r14+18h], 0
0x1401e5786  jl      loc_1401E6457
0x1401e578c  test    rsi, rsi
0x1401e578f  jz      loc_1401E62A8
0x1401e5795  mov     r8d, 28h ; '('; Size
0x1401e579b  mov     rax, [rsp+1E8h+var_148]
0x1401e57a3  cmp     [rax+10h], r8d
0x1401e57a7  jb      loc_1401E62C6
0x1401e57ad  test    bl, bl
0x1401e57af  jz      loc_1401E5A43
0x1401e57b5  mov     bl, [r13+40h]
0x1401e57b9  mov     [rsp+1E8h+var_178], 1
0x1401e57be  mov     rdx, [rax+20h]; Src
0x1401e57c2  lea     rcx, [rsp+1E8h+var_C0]; void *
0x1401e57ca  test    bl, bl
0x1401e57cc  jnz     loc_1401E605E
0x1401e57d2  call    RtlCopyVolatileMemory
0x1401e57d7  mov     rcx, [rsp+1E8h+var_148]
0x1401e57df  cmp     dword ptr [rcx+10h], 30h ; '0'
0x1401e57e3  jnb     loc_1401E5F10
0x1401e57e9  nop
0x1401e57ea  mov     [rsp+1E8h+var_178], 0
0x1401e57ef  mov     rax, qword ptr [rsp+1E8h+var_A0]
0x1401e57f7  cmp     rax, [r14+778h]
0x1401e57fe  jnz     loc_1401E6320
0x1401e5804  mov     eax, [rcx+8]
0x1401e5807  cmp     eax, 8
0x1401e580a  jb      loc_1401E633E
0x1401e5810  add     eax, 0FFFFFFF8h
0x1401e5813  mov     [rsp+1E8h+var_168], eax
0x1401e581a  mov     rax, [rsp+1E8h+var_120]
0x1401e5822  add     rax, 8
0x1401e5826  mov     [rsp+1E8h+var_160], rax
0x1401e582e  mov     [rsp+1E8h+var_150], 8
0x1401e5839  mov     eax, 702h
0x1401e583e  cmp     ax, [rsi]
0x1401e5841  mov     rcx, rsi
0x1401e5844  jnz     loc_1401E6117
0x1401e584a  mov     rcx, [rcx+68h]
0x1401e584e  mov     ebx, 40h ; '@'
0x1401e5853  add     rcx, rbx; Resource
0x1401e5856  mov     dl, 1; Wait
0x1401e5858  call    cs:__imp_ExAcquireResourceSharedLite
0x1401e585f  nop     dword ptr [rax+rax+00h]
0x1401e5864  mov     byte ptr [rsp+1E8h+var_176+1], 1
0x1401e5869  cmp     byte ptr [rsp+1E8h+var_176+3], 0
0x1401e586e  jnz     loc_1401E5A4A
0x1401e5874  test    dword ptr [rsi+200h], 10000h
0x1401e587e  jz      short loc_1401E589C
0x1401e5880  mov     al, cs:NtfsStatusDebugFlags
0x1401e5886  mov     edi, 0C000026Eh
0x1401e588b  test    al, al
0x1401e588d  jnz     loc_1401E5F86
0x1401e5893  mov     [rsp+1E8h+var_170], edi
0x1401e5897  jmp     loc_1401E64E4
0x1401e589c  mov     rdx, qword ptr [rsp+1E8h+var_C0]
0x1401e58a4  test    rdx, rdx
0x1401e58a7  jz      loc_1401E6475
0x1401e58ad  js      loc_1401E6439
0x1401e58b3  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1401e58bd  mov     rax, qword ptr [rsp+1E8h+var_B0+8]
0x1401e58c5  cmp     rax, rcx
0x1401e58c8  ja      loc_1401E6439
0x1401e58ce  add     rax, rdx
0x1401e58d1  js      loc_1401E6439
0x1401e58d7  mov     rax, [r14+788h]
0x1401e58de  cmp     rdx, rax
0x1401e58e1  jl      loc_1401E635C
0x1401e58e7  cmp     rdx, [rsi+20h]
0x1401e58eb  jl      loc_1401E5B57
0x1401e58f1  test    dword ptr [r14+4], 2000000h
0x1401e58f9  jnz     loc_1401E6393
0x1401e58ff  cmp     qword ptr [rsp+1E8h+var_B0+8], 0
0x1401e5908  jz      loc_1401E6132
0x1401e590e  lock inc dword ptr [rsi+0D4h]
0x1401e5915  mov     byte ptr [rsp+1E8h+var_176+2], 1
0x1401e591a  cmp     [rsp+1E8h+var_16C], 0
0x1401e591f  jnz     loc_1401E5A8C
0x1401e5925  mov     rbx, qword ptr [rsp+1E8h+var_B0+8]
0x1401e592d  add     rbx, qword ptr [rsp+1E8h+var_C0]
0x1401e5935  mov     al, cs:NtfsStatusDebugFlags
0x1401e593b  mov     edi, 103h
0x1401e5940  mov     edx, 78h ; 'x'; NumberOfBytes
0x1401e5945  mov     ecx, 210h; PoolType
0x1401e594a  mov     r8d, 7646744Eh; Tag
0x1401e5950  call    cs:__imp_ExAllocatePoolWithTag
0x1401e5957  nop     dword ptr [rax+rax+00h]
0x1401e595c  mov     r14, rax
0x1401e595f  xor     edx, edx; Val
0x1401e5961  lea     r8d, [rdx+48h]; Size
0x1401e5965  mov     rcx, rax; void *
0x1401e5968  call    memset
0x1401e596d  lea     rcx, [r14+48h]
0x1401e5971  movups  xmm0, [rsp+1E8h+var_C0]
0x1401e5979  movups  xmmword ptr [rcx], xmm0
0x1401e597c  movups  xmm1, [rsp+1E8h+var_B0]
0x1401e5984  movups  xmmword ptr [rcx+10h], xmm1
0x1401e5988  movups  xmm0, [rsp+1E8h+var_A0]
0x1401e5990  movups  xmmword ptr [rcx+20h], xmm0
0x1401e5994  mov     rax, [rsp+1E8h+var_148]
0x1401e599c  mov     [rax+20h], rcx
0x1401e59a0  mov     dword ptr [rax+10h], 30h ; '0'
0x1401e59a7  mov     [r14+30h], r13
0x1401e59ab  mov     [r14+10h], rbx
0x1401e59af  mov     [r14+38h], rsi
0x1401e59b3  mov     dword ptr [r14+40h], 0
0x1401e59bb  mov     dword ptr [r14+44h], 5
0x1401e59c3  cmp     byte ptr [rsp+1E8h+var_176], 0
0x1401e59c8  jz      short loc_1401E59D2
0x1401e59ca  mov     dword ptr [r14+44h], 7
0x1401e59d2  cmp     [r15+70h], r13
0x1401e59d6  jnz     short loc_1401E59EE
0x1401e59d8  mov     byte ptr [rsp+1E8h+Bcb], 1
0x1401e59dd  xor     r9d, r9d
0x1401e59e0  xor     r8d, r8d
0x1401e59e3  mov     rdx, r13
0x1401e59e6  mov     rcx, r15
0x1401e59e9  call    NtfsPrePostIrpInternal
0x1401e59ee  lea     rbx, [rsi+0A0h]
0x1401e59f5  lea     rcx, [rsi+78h]
0x1401e59f9  mov     rdx, rbx
0x1401e59fc  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401e5a03  nop     dword ptr [rax+rax+00h]
0x1401e5a08  mov     r9d, 1
0x1401e5a0e  mov     r8, r14
0x1401e5a11  lea     rdx, NtfsCancelReadUsnJournal
0x1401e5a18  mov     rcx, r13
0x1401e5a1b  call    NtfsSetCancelRoutine
0x1401e5a20  test    al, al
0x1401e5a22  jz      loc_1401E60C5
0x1401e5a28  lea     rax, [rsi+250h]
0x1401e5a2f  mov     rdx, [rax+8]
0x1401e5a33  cmp     [rdx], rax
0x1401e5a36  jz      loc_1401E622C
0x1401e5a3c  mov     ecx, 3
0x1401e5a41  int     29h; Win8: RtlFailFast(ecx)
0x1401e5a43  xor     bl, bl
0x1401e5a45  jmp     loc_1401E57B9
0x1401e5a4a  mov     rdx, r14
0x1401e5a4d  mov     rcx, r15
0x1401e5a50  call    NtfsReleaseVcb
0x1401e5a55  mov     byte ptr [rsp+1E8h+var_176+3], 0
0x1401e5a5a  jmp     loc_1401E5874
0x1401e5a5f  lea     rax, [r9+3]
0x1401e5a63  and     rax, 0FFFFFFFFFFFFFFFCh
0x1401e5a67  cmp     r9, rax
0x1401e5a6a  jz      loc_1401E575A
0x1401e5a70  mov     al, cs:NtfsStatusDebugFlags
0x1401e5a76  mov     edi, 0C000000Dh
0x1401e5a7b  test    al, al
0x1401e5a7d  jnz     loc_1401E618A
0x1401e5a83  mov     [rsp+1E8h+var_170], edi
0x1401e5a87  jmp     loc_1401E610D
0x1401e5a8c  cmp     r13, [r15+70h]
0x1401e5a90  jnz     loc_1401E5925
0x1401e5a96  mov     eax, 702h
0x1401e5a9b  cmp     ax, [rsi]
0x1401e5a9e  jz      loc_1401E648C
0x1401e5aa4  mov     rcx, [rsi+8]; Resource
0x1401e5aa8  call    cs:__imp_ExReleaseResourceLite
0x1401e5aaf  nop     dword ptr [rax+rax+00h]
0x1401e5ab4  mov     byte ptr [rsp+1E8h+var_176+1], 0
0x1401e5ab9  mov     rax, qword ptr [rsp+1E8h+var_B0]
0x1401e5ac1  neg     rax
0x1401e5ac4  sbb     r8, r8
0x1401e5ac7  lea     rax, [rsp+1E8h+var_B0]
0x1401e5acf  and     r8, rax; int
0x1401e5ad2  mov     rdx, qword ptr [rsp+1E8h+var_B0+8]
0x1401e5ada  add     rdx, qword ptr [rsp+1E8h+var_C0]; int
0x1401e5ae2  mov     [rsp+1E8h+var_1B8], r8; PLARGE_INTEGER
0x1401e5ae7  mov     [rsp+1E8h+Bcb], r13; __int64
0x1401e5aec  mov     r9b, byte ptr [rsp+1E8h+var_176]; int
0x1401e5af1  mov     rcx, rsi; int
0x1401e5af4  call    NtOfsWaitForNewLength
0x1401e5af9  mov     edi, eax
0x1401e5afb  mov     [rsp+1E8h+var_170], eax
0x1401e5aff  test    eax, eax
0x1401e5b01  jnz     loc_1401E64E4
0x1401e5b07  mov     eax, 702h
0x1401e5b0c  cmp     ax, [rsi]
0x1401e5b0f  mov     rcx, rsi
0x1401e5b12  jnz     loc_1401E6220
0x1401e5b18  mov     rcx, [rcx+68h]
0x1401e5b1c  add     rcx, rbx; Resource
0x1401e5b1f  mov     dl, 1; Wait
0x1401e5b21  call    cs:__imp_ExAcquireResourceSharedLite
0x1401e5b28  nop     dword ptr [rax+rax+00h]
0x1401e5b2d  mov     byte ptr [rsp+1E8h+var_176+1], 1
0x1401e5b32  lock dec dword ptr [rsi+0D4h]
0x1401e5b39  mov     byte ptr [rsp+1E8h+var_176+2], 0
0x1401e5b3e  mov     rax, [rsi+0C0h]
0x1401e5b45  cmp     rsi, [rax+28h]
0x1401e5b49  jnz     loc_1401E6498
0x1401e5b4f  mov     rdx, qword ptr [rsp+1E8h+var_C0]
0x1401e5b57  mov     eax, [rsp+1E8h+var_168]
0x1401e5b5e  test    eax, eax
0x1401e5b60  jz      loc_1401E612D
0x1401e5b66  mov     rbx, [rsi+20h]
0x1401e5b6a  cmp     rdx, rbx
0x1401e5b6d  jge     loc_1401E61EE
0x1401e5b73  mov     qword ptr [rsp+1E8h+FileOffset], 0
0x1401e5b7f  mov     [rsp+1E8h+var_16B], 0
0x1401e5b84  mov     [rsp+1E8h+var_100], 0
0x1401e5b90  sub     rbx, rdx
0x1401e5b93  mov     [rsp+1E8h+var_130], rbx
0x1401e5b9b  mov     ecx, edx
0x1401e5b9d  and     ecx, 3FFFFh
0x1401e5ba3  mov     eax, 40000h
0x1401e5ba8  sub     eax, ecx
  ... truncated ...
```
