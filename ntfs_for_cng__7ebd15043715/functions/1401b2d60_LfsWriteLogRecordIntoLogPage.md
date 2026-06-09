# LfsWriteLogRecordIntoLogPage

- ea: `0x1401b2d60`
- end: `0x1401b398f`
- name: `LfsWriteLogRecordIntoLogPage`
- size: `3119`
- prototype: `__int64 __fastcall(__int64, __int64, int, char **, int, _DWORD *, unsigned __int64, unsigned __int64, int, unsigned __int16, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401b2830`
- `0x1401b4080`

## callees

- `0x140027f08`
- `0x14002f140`
- `0x14004134c`
- `0x1400593c0`
- `0x1400596c0`
- `0x1401b2d60`
- `0x1401b39a0`
- `0x1401b3c08`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401b38e9`
- `ntoskrnl!KeSetEvent` at `0x1401b38e9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401b2dc9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401b2dc9`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b3642`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b36a7`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b3642`
- `ntoskrnl!KeSetPriorityThread` at `0x1401b36a7`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401b3651`
- `ntoskrnl!PsEnterPriorityRegion` at `0x1401b3651`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401b3685`
- `ntoskrnl!PsLeavePriorityRegion` at `0x1401b3685`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b3081`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b3081`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b2f4c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b305d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b3929`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b2f4c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b305d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b3929`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b3898`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401b3898`
- `ntoskrnl!KeInitializeEvent` at `0x1401b3576`
- `ntoskrnl!KeInitializeEvent` at `0x1401b3576`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b35c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b3668`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b3867`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b35c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b3668`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401b3867`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401b35a9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401b35a9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b30a7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b38b2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b30a7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401b38b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b3095`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b3095`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b306d`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b358e`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b306d`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401b358e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b3911`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b3911`
- `ntoskrnl!ExRaiseStatus` at `0x1401b393c`
- `ntoskrnl!ExRaiseStatus` at `0x1401b396e`
- `ntoskrnl!ExRaiseStatus` at `0x1401b393c`
- `ntoskrnl!ExRaiseStatus` at `0x1401b396e`

## pseudocode

```c
__int64 __fastcall LfsWriteLogRecordIntoLogPage(
        __int64 a1,
        __int64 a2,
        int a3,
        char **a4,
        int a5,
        _DWORD *a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        int a9,
        unsigned __int16 a10,
        unsigned __int64 *a11)
{
  int v11; // edi
  char **v13; // r14
  char **i; // rcx
  __int64 v16; // rsi
  __int64 v17; // rbx
  int v18; // esi
  int v19; // r15d
  unsigned int v20; // esi
  unsigned __int16 v21; // r12
  int v22; // esi
  __int64 v23; // r8
  __int64 v24; // r10
  __int64 v25; // r13
  unsigned __int64 v26; // rdx
  int v27; // r9d
  __int16 v28; // cx
  unsigned int v29; // esi
  unsigned __int64 *v30; // rbx
  unsigned int v31; // r15d
  __int64 v32; // rax
  unsigned __int64 v33; // rsi
  _DWORD *v34; // rax
  int v35; // eax
  unsigned int v36; // esi
  int v37; // ebx
  __int64 v38; // rcx
  char v40; // r15
  __int64 Lbcb; // r8
  _DWORD *v42; // rdx
  unsigned int v43; // ebx
  __int16 v44; // r15
  __int64 *v45; // rax
  unsigned int v46; // ecx
  unsigned int v47; // r9d
  __int64 v48; // r12
  unsigned int v49; // r9d
  int v50; // r8d
  unsigned __int64 v51; // rbx
  __int64 v52; // rax
  unsigned __int64 *v53; // r15
  _DWORD *v54; // rax
  int v55; // eax
  unsigned int v56; // r13d
  unsigned int v57; // r8d
  char *v58; // r11
  int v59; // edx
  int v60; // r9d
  int v61; // r10d
  _QWORD *v62; // r8
  unsigned int v63; // eax
  void *v64; // r9
  unsigned int v65; // ecx
  char *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // r9
  unsigned int v69; // ecx
  __int64 v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rbx
  __int64 *v73; // rax
  struct _ERESOURCE *v74; // rcx
  BOOLEAN IsResourceAcquiredExclusiveLite; // r12
  __int64 v76; // rcx
  unsigned int v77; // ecx
  KPRIORITY v78; // r12d
  _DWORD *v79; // rax
  __int64 v80; // rcx
  __int64 *v81; // rax
  __int64 v82; // rcx
  _QWORD *v83; // rax
  _QWORD *v84; // rcx
  __int64 v85; // r11
  _QWORD *j; // rax
  _QWORD *v87; // rcx
  struct _ERESOURCE *v88; // rcx
  struct _KEVENT *v89; // rcx
  char *v90; // [rsp+30h] [rbp-A8h]
  __int64 v91; // [rsp+38h] [rbp-A0h]
  unsigned int v92; // [rsp+40h] [rbp-98h]
  int v93; // [rsp+44h] [rbp-94h]
  int v94; // [rsp+48h] [rbp-90h]
  unsigned int v95; // [rsp+4Ch] [rbp-8Ch]
  __int128 v96; // [rsp+50h] [rbp-88h] BYREF
  _BYTE Event[32]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v98; // [rsp+80h] [rbp-58h]
  unsigned int v99; // [rsp+E0h] [rbp+8h]
  int v100; // [rsp+E0h] [rbp+8h]
  unsigned int v102; // [rsp+E8h] [rbp+10h]
  unsigned int v103; // [rsp+E8h] [rbp+10h]
  NTSTATUS Status; // [rsp+F0h] [rbp+18h] BYREF
  unsigned __int64 v105; // [rsp+F8h] [rbp+20h]

  v11 = 0;
  Status = 0;
  v13 = a4;
  for ( i = a4; a3; i += 2 )
  {
    --a3;
    if ( *i )
      v11 += (*((_DWORD *)i + 2) + 7) & 0xFFFFFFF8;
  }
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
  v16 = a1 + 144;
  v17 = *(_QWORD *)(a1 + 144);
  if ( v17 != a1 + 144 )
  {
    v18 = *(_DWORD *)(a1 + 40);
    v19 = *(_DWORD *)(a1 + 44) & *(_DWORD *)(v17 + 40);
    if ( v19 )
      v20 = v18 - v19;
    else
      v20 = v18 - *(_DWORD *)(a1 + 80);
    if ( v11 + (unsigned int)*(unsigned __int16 *)(a1 + 96) <= v20 )
    {
      v21 = a10;
      v99 = LfsVerifyLogSpaceAvail(a1, a2, v11, a9, a10 & 1, (__int64)&Status);
      if ( Status )
      {
        ExReleasePushLockEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
        ExRaiseStatus(Status);
      }
      v22 = v20 - *(unsigned __int16 *)(a1 + 96);
      if ( !v19 )
      {
        *(_QWORD *)(a1 + 400) -= *(_QWORD *)(a1 + 408);
        *(_DWORD *)(v17 + 40) += *(_DWORD *)(a1 + 80);
        v19 = *(_DWORD *)(a1 + 80);
      }
      v23 = *(unsigned int *)(v17 + 40);
      v24 = *(_QWORD *)(v17 + 48);
      v25 = v24 + (unsigned int)(*(_DWORD *)(v17 + 40) - v19);
      v26 = ((unsigned __int64)(v23 + *(_QWORD *)(v17 + 16)) >> 3) + (*(_QWORD *)(v17 + 32) << *(_DWORD *)(a1 + 124));
      v105 = v26;
      if ( a5 == 2 && *(__int16 *)(a1 + 422) > 1 )
        *(_DWORD *)(v25 + 16) |= 2u;
      v27 = *(unsigned __int16 *)(a1 + 96);
      *(_DWORD *)(v17 + 80) |= 1u;
      *(_DWORD *)(v17 + 40) += v27 + v11;
      *(_DWORD *)(v25 + 16) |= 1u;
      *(_QWORD *)(v17 + 72) = v26;
      if ( (*(_DWORD *)(a1 + 428) & 8) != 0 )
      {
        *(_QWORD *)(v25 + 32) = v26;
        v28 = *(_WORD *)(a1 + 44) & *(_WORD *)(v17 + 40);
        *(_WORD *)(v25 + 24) = v28;
        if ( !v28 )
          *(_WORD *)(v25 + 24) = 4096;
      }
      *(_QWORD *)(v17 + 64) = v26;
      v29 = v22 - v11;
      *(_QWORD *)(v25 + 8) = v26;
      if ( v29 >= *(unsigned __int16 *)(a1 + 96) )
        goto LABEL_17;
      v77 = v29 + *(_DWORD *)(v17 + 40);
      if ( v77 < *(_DWORD *)(v17 + 24) )
      {
        *(_DWORD *)(v17 + 40) = v77;
LABEL_17:
        v30 = (unsigned __int64 *)(v24 + v23);
        v31 = v27 + v19;
        **(_QWORD **)(a1 + 200) = v26;
        v32 = *(_QWORD *)(a1 + 200);
        *(_DWORD *)(a1 + 548) = 1;
        *(_DWORD *)(v32 + 32) = v11;
        if ( (*(_DWORD *)(a1 + 428) & 4) != 0 )
          *(_DWORD *)(a1 + 428) &= ~4u;
        ExReleasePushLockEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
        v33 = v105;
        *a11 = v105;
        memset(v30, 0, *(unsigned __int16 *)(a1 + 96));
        v30[1] = a8;
        v30[2] = a7;
        v34 = a6;
        *v30 = v33;
        if ( v34 )
          *((_DWORD *)v30 + 9) = *v34;
        *((_DWORD *)v30 + 6) = v11;
        v35 = *(_DWORD *)(a2 + 32);
        *((_WORD *)v30 + 20) |= (v21 >> 1) & 6;
        *((_DWORD *)v30 + 7) = v35;
        for ( *((_DWORD *)v30 + 8) = a5; v11; v13 += 2 )
        {
          if ( *v13 )
          {
            v36 = *((_DWORD *)v13 + 2);
            v37 = -v36 & 7;
            memmove((void *)(v25 + v31), *v13, v36);
            v31 += v36 + v37;
            v11 -= v36 + v37;
          }
        }
        v38 = *(unsigned int *)(a1 + 428);
        if ( (v38 & 0x4000000) != 0 )
          LfsComputeLogPageChecksum(v38, v25, *(_DWORD *)(a1 + 40));
        return v99;
      }
      v83 = (_QWORD *)(a1 + 144);
      v84 = *(_QWORD **)(a1 + 144);
      if ( v84[1] == a1 + 144 )
      {
        v85 = *v84;
        if ( *(_QWORD **)(*v84 + 8LL) == v84 )
        {
          *v83 = v85;
          *(_QWORD *)(v85 + 8) = v83;
          *(_DWORD *)(v17 + 84) &= ~2u;
          *(_DWORD *)(v17 + 40) += v29;
          goto LABEL_17;
        }
      }
LABEL_54:
      __fastfail(3u);
    }
    v16 = a1 + 144;
  }
  ExReleasePushLockEx(*(_QWORD *)(a2 + 56) + 104LL, 0);
  if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a2 + 56)) )
  {
    if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a2 + 56)) )
      ExReleaseResourceLite(*(PERESOURCE *)(a2 + 56));
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a2 + 56), 1u);
  }
  v40 = a10;
  v95 = LfsVerifyLogSpaceAvail(a1, a2, v11, a9, a10 & 1, (__int64)&Status);
  if ( Status )
    ExRaiseStatus(Status);
  v42 = *(_DWORD **)v16;
  v43 = v11 + *(unsigned __int16 *)(a1 + 96);
  if ( *(_QWORD *)v16 != v16
    && v43 > v42[6] - v42[10]
    && (*(_DWORD *)(a1 + 428) & 8) == 0
    && v42[10] != *(_DWORD *)(a1 + 80) )
  {
    v79 = *(_DWORD **)v16;
    if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) != v16 )
      goto LABEL_54;
    v80 = *(_QWORD *)v79;
    if ( *(_DWORD **)(*(_QWORD *)v79 + 8LL) != v79 )
      goto LABEL_54;
    *(_QWORD *)v16 = v80;
    *(_QWORD *)(v80 + 8) = v16;
    v42[21] &= ~2u;
  }
  v44 = v40 & 2;
  Status = v43;
LABEL_37:
  v45 = *(__int64 **)v16;
  while ( 1 )
  {
    if ( v45 == (__int64 *)v16 )
    {
      LOBYTE(Lbcb) = v44 != 0;
      Lbcb = LfsAllocateLbcb(a1, 1, Lbcb, 0);
      if ( !Lbcb )
      {
        v72 = LfsLiMax;
        v98 = 0;
        v96 = 0;
        memset(Event, 0, sizeof(Event));
        v73 = *(__int64 **)(a1 + 200);
        if ( LfsLiMax > *v73 )
          v72 = *v73;
        KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
        v74 = *(struct _ERESOURCE **)(a1 + 456);
        *(_QWORD *)&Event[24] = v72;
        IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(v74);
        while ( 1 )
        {
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 456) + 120LL));
          v76 = *(_QWORD *)(a1 + 456);
          if ( v72 <= *(_QWORD *)(a1 + 280) )
          {
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v76 + 120));
LABEL_90:
            v43 = Status;
            goto LABEL_37;
          }
          if ( !*(_DWORD *)(v76 + 176) )
            break;
          for ( j = *(_QWORD **)(a1 + 472); j != (_QWORD *)(a1 + 472); j = (_QWORD *)*j )
          {
            if ( j[5] > v72 )
              break;
          }
          v87 = (_QWORD *)j[1];
          if ( (_QWORD *)*v87 != j )
            goto LABEL_54;
          *((_QWORD *)&v96 + 1) = j[1];
          *(_QWORD *)&v96 = j;
          *v87 = &v96;
          j[1] = &v96;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 456) + 120LL));
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 464));
          LfsReleaseLfcb(a1);
          KeWaitForSingleObject(Event, Executive, 0, 0, 0);
          v88 = *(struct _ERESOURCE **)(a1 + 456);
          if ( IsResourceAcquiredExclusiveLite )
            ExAcquireResourceExclusiveLite(v88, 1u);
          else
            ExAcquireResourceSharedLite(v88, 1u);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 464), 0xFFFFFFFF) == 1 )
          {
            v89 = *(struct _KEVENT **)(a1 + 608);
            if ( v89 )
              KeSetEvent(v89, 0, 0);
          }
        }
        *(_DWORD *)(v76 + 176) = 1;
        *(_QWORD *)(a1 + 504) = KeGetCurrentThread();
        v78 = KeSetPriorityThread(KeGetCurrentThread(), 16);
        PsEnterPriorityRegion();
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 456) + 120LL));
        LfsFlushLfcbOnNewStack(a1, v72, 0, 1);
        PsLeavePriorityRegion();
        if ( v78 == 16 )
          goto LABEL_90;
        KeSetPriorityThread(KeGetCurrentThread(), v78);
        v43 = Status;
        goto LABEL_37;
      }
    }
    else
    {
      Lbcb = (__int64)(v45 - 3);
    }
    v46 = *(_DWORD *)(Lbcb + 48) - *(_DWORD *)(Lbcb + 64);
    v47 = *(_DWORD *)(a1 + 40);
    if ( v46 >= v47 )
      v46 -= *(_DWORD *)(a1 + 80) * (v46 / v47);
    if ( v46 >= v43 )
      break;
    v45 = *(__int64 **)(Lbcb + 24);
    v43 -= v46;
  }
  v48 = *(_QWORD *)v16 - 24LL;
  v94 = v11;
  v49 = *(_DWORD *)(v48 + 64);
  v50 = *(_DWORD *)(a1 + 44) & v49;
  if ( v50 )
  {
    LOBYTE(Status) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 400) -= *(_QWORD *)(a1 + 408);
    *(_DWORD *)(v48 + 64) += *(_DWORD *)(a1 + 80);
    v49 = *(_DWORD *)(v48 + 64);
    v50 = *(_DWORD *)(a1 + 80);
    LOBYTE(Status) = 1;
  }
  v102 = *(_DWORD *)(a1 + 40) - v50;
  v51 = (((unsigned __int64)v49 + *(_QWORD *)(v48 + 40)) >> 3) + (*(_QWORD *)(v48 + 56) << *(_DWORD *)(a1 + 124));
  v52 = *(_QWORD *)(v48 + 72);
  v91 = v52 + v49 - v50;
  v53 = (unsigned __int64 *)(v52 + v49);
  if ( a5 == 2 && *(__int16 *)(a1 + 422) > 1 )
    *(_DWORD *)(v52 + v49 - v50 + 16) |= 2u;
  memset(v53, 0, *(unsigned __int16 *)(a1 + 96));
  v53[1] = a8;
  v53[2] = a7;
  v54 = a6;
  *v53 = v51;
  if ( v54 )
    *((_DWORD *)v53 + 9) = *v54;
  *((_DWORD *)v53 + 6) = v11;
  *((_DWORD *)v53 + 7) = *(_DWORD *)(a2 + 32);
  *((_DWORD *)v53 + 8) = a5;
  *((_WORD *)v53 + 20) |= (a10 >> 1) & 6;
  if ( v11 + (unsigned int)*(unsigned __int16 *)(a1 + 96) > v102 )
    *((_WORD *)v53 + 20) |= 1u;
  v55 = *(unsigned __int16 *)(a1 + 96);
  *(_DWORD *)(v48 + 64) += v55;
  v56 = v102 - v55;
  v57 = *((_DWORD *)v13 + 2);
  v58 = *v13;
  v59 = -v57 & 7;
  LODWORD(v105) = *(unsigned __int16 *)(a1 + 96);
  v90 = v58;
  v103 = v57;
  v100 = v59;
  if ( v11 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( !v58 )
          {
            v57 = *((_DWORD *)v13 + 6);
            v13 += 2;
            v103 = v57;
            v59 = -v57 & 7;
            v58 = *v13;
            v100 = v59;
            v90 = *v13;
            goto LABEL_75;
          }
          v60 = *(_DWORD *)(v48 + 64);
          v61 = *(_DWORD *)(a1 + 44);
          if ( (*(_DWORD *)(v48 + 108) & 4) != 0 )
          {
            v63 = *(_DWORD *)(v48 + 64);
          }
          else
          {
            v62 = *(_QWORD **)(a1 + 136);
            if ( *v62 != a1 + 128 )
              goto LABEL_54;
            *(_QWORD *)(v48 + 16) = v62;
            *(_QWORD *)(v48 + 8) = a1 + 128;
            *v62 = v48 + 8;
            v57 = v103;
            *(_QWORD *)(a1 + 136) = v48 + 8;
            *(_DWORD *)(v48 + 108) |= 4u;
            v63 = *(_DWORD *)(v48 + 64);
          }
          if ( !(_DWORD)v105 && (v61 & v60) == 0 )
          {
            *(_QWORD *)(a1 + 400) -= *(_QWORD *)(a1 + 408);
            *(_DWORD *)(v48 + 64) += *(_DWORD *)(a1 + 80);
            v63 = *(_DWORD *)(v48 + 64);
            LOBYTE(Status) = 1;
          }
          v64 = (void *)(v63 + *(_QWORD *)(v48 + 72));
          LODWORD(v105) = 0;
          if ( v57 > v56 )
          {
            v93 = 0;
            v65 = v56;
            v92 = v56;
            v90 = &v58[v56];
            v103 = v57 - v56;
          }
          else
          {
            v93 = v59;
            v65 = v57;
            v92 = v57;
            if ( v11 != v59 + v57 )
            {
              v66 = v13[2];
              v13 += 2;
              v90 = v66;
              v103 = *((_DWORD *)v13 + 2);
              v100 = -v103 & 7;
            }
          }
          memmove(v64, v58, v65);
          v67 = v92;
          v68 = v91;
          v11 -= v93 + v92;
          v56 -= v93 + v92;
          *(_DWORD *)(v48 + 64) += v93 + v92;
          if ( (_BYTE)Status && !v56 )
            *(_DWORD *)(v91 + 16) &= ~1u;
          if ( !v11 )
          {
            *(_DWORD *)(v48 + 104) |= 1u;
            *(_DWORD *)(v91 + 16) |= 1u;
            *(_QWORD *)(v48 + 96) = v51;
            if ( (*(_DWORD *)(a1 + 428) & 8) != 0 )
            {
              *(_QWORD *)(v91 + 32) = v51;
              v67 = *(unsigned __int16 *)(a1 + 44);
              LOWORD(v67) = *(_WORD *)(v48 + 64) & v67;
              *(_WORD *)(v91 + 24) = v67;
              if ( !(_WORD)v67 )
                *(_WORD *)(v91 + 24) = 4096;
            }
          }
          if ( !v56 )
            break;
          v59 = v100;
          v57 = v103;
          v58 = v90;
        }
        while ( v11 );
        *(_QWORD *)(v48 + 88) = v51;
        *(_QWORD *)(v91 + 8) = v51;
        if ( (*(_DWORD *)(a1 + 428) & 0x4000000) != 0 )
        {
          LfsComputeLogPageChecksum(v67, v91, *(_DWORD *)(a1 + 40));
          v68 = v91;
        }
        if ( v56 < *(unsigned __int16 *)(a1 + 96) )
          break;
LABEL_74:
        v58 = v90;
        v57 = v103;
        v59 = v100;
LABEL_75:
        if ( !v11 )
          goto LABEL_76;
      }
      v69 = v56 + *(_DWORD *)(v48 + 64);
      if ( v69 < *(_DWORD *)(v48 + 48) )
      {
        v70 = *(unsigned int *)(a1 + 40);
        *(_DWORD *)(v48 + 64) = v69;
        v56 = *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 80);
        v91 = v70 + v68;
        goto LABEL_74;
      }
      v81 = *(__int64 **)v16;
      if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) != v16 )
        goto LABEL_54;
      v82 = *v81;
      if ( *(__int64 **)(*v81 + 8) != v81 )
        goto LABEL_54;
      *(_QWORD *)v16 = v82;
      *(_QWORD *)(v82 + 8) = v16;
      *(_DWORD *)(v48 + 108) &= ~2u;
      *(_DWORD *)(v48 + 64) += v56;
      if ( !v11 )
        break;
      v48 = *(_QWORD *)v16 - 24LL;
      v56 = *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 80);
      v59 = v100;
      v57 = v103;
      v58 = v90;
      v91 = *(_QWORD *)(v48 + 72);
    }
  }
LABEL_76:
  *a11 = v51;
  **(_QWORD **)(a1 + 200) = v51;
  v71 = *(_QWORD *)(a1 + 200);
  *(_DWORD *)(a1 + 548) = 1;
  *(_DWORD *)(v71 + 32) = v94;
  if ( (*(_DWORD *)(a1 + 428) & 4) != 0 )
    *(_DWORD *)(a1 + 428) &= ~4u;
  return v95;
}

```

## disassembly

```asm
0x1401b2d60  mov     [rsp+arg_8], rdx
0x1401b2d65  push    rbx
0x1401b2d66  push    rbp
0x1401b2d67  push    rsi
0x1401b2d68  push    rdi
0x1401b2d69  push    r13
0x1401b2d6b  push    r14
0x1401b2d6d  sub     rsp, 0A8h
0x1401b2d74  xor     edi, edi
0x1401b2d76  mov     [rsp+0D8h+Status], 0
0x1401b2d81  mov     rbp, rcx
0x1401b2d84  mov     r14, r9
0x1401b2d87  mov     r13, rdx
0x1401b2d8a  mov     rcx, r9
0x1401b2d8d  test    r8d, r8d
0x1401b2d90  jz      short loc_1401B2DAF
0x1401b2d92  dec     r8d
0x1401b2d95  cmp     qword ptr [rcx], 0
0x1401b2d99  jz      short loc_1401B2DA6
0x1401b2d9b  mov     eax, [rcx+8]
0x1401b2d9e  add     eax, 7
0x1401b2da1  and     eax, 0FFFFFFF8h
0x1401b2da4  add     edi, eax
0x1401b2da6  add     rcx, 10h
0x1401b2daa  test    r8d, r8d
0x1401b2dad  jnz     short loc_1401B2D92
0x1401b2daf  mov     rcx, [rdx+38h]
0x1401b2db3  xor     edx, edx
0x1401b2db5  add     rcx, 68h ; 'h'
0x1401b2db9  mov     [rsp+0D8h+var_38], r12
0x1401b2dc1  mov     [rsp+0D8h+var_40], r15
0x1401b2dc9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401b2dd0  nop     dword ptr [rax+rax+00h]
0x1401b2dd5  lea     rsi, [rbp+90h]
0x1401b2ddc  mov     rbx, [rsi]
0x1401b2ddf  cmp     rbx, rsi
0x1401b2de2  jz      loc_1401B3053
0x1401b2de8  mov     r15d, [rbx+28h]
0x1401b2dec  mov     esi, [rbp+28h]
0x1401b2def  and     r15d, [rbp+2Ch]
0x1401b2df3  jz      loc_1401B3504
0x1401b2df9  sub     esi, r15d
0x1401b2dfc  movzx   eax, word ptr [rbp+60h]
0x1401b2e00  add     eax, edi
0x1401b2e02  cmp     eax, esi
0x1401b2e04  ja      loc_1401B304C
0x1401b2e0a  movzx   r12d, [rsp+0D8h+arg_48]
0x1401b2e13  lea     rcx, [rsp+0D8h+Status]
0x1401b2e1b  mov     r9d, [rsp+0D8h+arg_40]
0x1401b2e23  movzx   eax, r12b
0x1401b2e27  mov     [rsp+0D8h+var_B0], rcx
0x1401b2e2c  and     al, 1
0x1401b2e2e  mov     r8d, edi
0x1401b2e31  mov     byte ptr [rsp+0D8h+Timeout], al
0x1401b2e35  mov     rdx, r13
0x1401b2e38  mov     rcx, rbp
0x1401b2e3b  call    LfsVerifyLogSpaceAvail
0x1401b2e40  cmp     [rsp+0D8h+Status], 0
0x1401b2e48  mov     [rsp+0D8h+arg_0], eax
0x1401b2e4f  jnz     loc_1401B391F
0x1401b2e55  movzx   eax, word ptr [rbp+60h]
0x1401b2e59  sub     esi, eax
0x1401b2e5b  test    r15d, r15d
0x1401b2e5e  jnz     short loc_1401B2E78
0x1401b2e60  mov     rax, [rbp+198h]
0x1401b2e67  sub     [rbp+190h], rax
0x1401b2e6e  mov     eax, [rbp+50h]
0x1401b2e71  add     [rbx+28h], eax
0x1401b2e74  mov     r15d, [rbp+50h]
0x1401b2e78  mov     r8d, [rbx+28h]
0x1401b2e7c  mov     rax, [rbx+10h]
0x1401b2e80  mov     r13d, r8d
0x1401b2e83  mov     rdx, [rbx+20h]
0x1401b2e87  add     rax, r8
0x1401b2e8a  mov     ecx, [rbp+7Ch]
0x1401b2e8d  sub     r13d, r15d
0x1401b2e90  mov     r10, [rbx+30h]
0x1401b2e94  shr     rax, 3
0x1401b2e98  add     r13, r10
0x1401b2e9b  shl     rdx, cl
0x1401b2e9e  add     rdx, rax
0x1401b2ea1  cmp     [rsp+0D8h+arg_20], 2
0x1401b2ea9  mov     [rsp+0D8h+arg_18], rdx
0x1401b2eb1  jz      loc_1401B379F
0x1401b2eb7  movzx   r9d, word ptr [rbp+60h]
0x1401b2ebc  or      dword ptr [rbx+50h], 1
0x1401b2ec0  lea     eax, [r9+rdi]
0x1401b2ec4  add     [rbx+28h], eax
0x1401b2ec7  or      dword ptr [r13+10h], 1
0x1401b2ecc  mov     [rbx+48h], rdx
0x1401b2ed0  mov     eax, [rbp+1ACh]
0x1401b2ed6  test    al, 8
0x1401b2ed8  jz      short loc_1401B2EF1
0x1401b2eda  mov     [r13+20h], rdx
0x1401b2ede  movzx   ecx, word ptr [rbx+28h]
0x1401b2ee2  and     cx, [rbp+2Ch]
0x1401b2ee6  mov     [r13+18h], cx
0x1401b2eeb  jz      loc_1401B3040
0x1401b2ef1  mov     [rbx+40h], rdx
0x1401b2ef5  sub     esi, edi
0x1401b2ef7  mov     [r13+8], rdx
0x1401b2efb  movzx   eax, word ptr [rbp+60h]
0x1401b2eff  cmp     esi, eax
0x1401b2f01  jb      loc_1401B35E1
0x1401b2f07  mov     rax, [rbp+0C8h]
0x1401b2f0e  lea     rbx, [r10+r8]
0x1401b2f12  add     r15d, r9d
0x1401b2f15  mov     [rax], rdx
0x1401b2f18  mov     rax, [rbp+0C8h]
0x1401b2f1f  mov     dword ptr [rbp+224h], 1
0x1401b2f29  mov     [rax+20h], edi
0x1401b2f2c  mov     eax, [rbp+1ACh]
0x1401b2f32  test    al, 4
0x1401b2f34  jnz     loc_1401B3949
0x1401b2f3a  mov     rcx, [rsp+0D8h+arg_8]
0x1401b2f42  xor     edx, edx
0x1401b2f44  mov     rcx, [rcx+38h]
0x1401b2f48  add     rcx, 68h ; 'h'
0x1401b2f4c  call    cs:__imp_ExReleasePushLockEx
0x1401b2f53  nop     dword ptr [rax+rax+00h]
0x1401b2f58  mov     rax, [rsp+0D8h+arg_50]
0x1401b2f60  xor     edx, edx; Val
0x1401b2f62  mov     rsi, [rsp+0D8h+arg_18]
0x1401b2f6a  mov     rcx, rbx; void *
0x1401b2f6d  mov     [rax], rsi
0x1401b2f70  movzx   r8d, word ptr [rbp+60h]; Size
0x1401b2f75  call    memset
0x1401b2f7a  mov     rax, [rsp+0D8h+arg_38]
0x1401b2f82  mov     [rbx+8], rax
0x1401b2f86  mov     rax, [rsp+0D8h+arg_30]
0x1401b2f8e  mov     [rbx+10h], rax
0x1401b2f92  mov     rax, [rsp+0D8h+arg_28]
0x1401b2f9a  mov     [rbx], rsi
0x1401b2f9d  test    rax, rax
0x1401b2fa0  jz      short loc_1401B2FA7
0x1401b2fa2  mov     eax, [rax]
0x1401b2fa4  mov     [rbx+24h], eax
0x1401b2fa7  mov     rax, [rsp+0D8h+arg_8]
0x1401b2faf  shr     r12w, 1
0x1401b2fb3  and     r12w, 6
0x1401b2fb8  mov     [rbx+18h], edi
0x1401b2fbb  mov     eax, [rax+20h]
0x1401b2fbe  or      [rbx+28h], r12w
0x1401b2fc3  mov     [rbx+1Ch], eax
0x1401b2fc6  mov     eax, [rsp+0D8h+arg_20]
0x1401b2fcd  mov     [rbx+20h], eax
0x1401b2fd0  test    edi, edi
0x1401b2fd2  jz      short loc_1401B3008
0x1401b2fd4  mov     rdx, [r14]; Src
0x1401b2fd7  test    rdx, rdx
0x1401b2fda  jz      short loc_1401B3000
0x1401b2fdc  mov     esi, [r14+8]
0x1401b2fe0  mov     ebx, esi
0x1401b2fe2  mov     ecx, r15d
0x1401b2fe5  neg     ebx
0x1401b2fe7  mov     r8d, esi; Size
0x1401b2fea  add     rcx, r13; void *
0x1401b2fed  and     ebx, 7
0x1401b2ff0  call    memmove
0x1401b2ff5  lea     eax, [rsi+rbx]
0x1401b2ff8  add     r15d, eax
0x1401b2ffb  lea     eax, [rsi+rbx]
0x1401b2ffe  sub     edi, eax
0x1401b3000  add     r14, 10h
0x1401b3004  test    edi, edi
0x1401b3006  jnz     short loc_1401B2FD4
0x1401b3008  mov     ecx, [rbp+1ACh]
0x1401b300e  bt      ecx, 1Ah
0x1401b3012  jb      loc_1401B395D
0x1401b3018  mov     eax, [rsp+0D8h+arg_0]
0x1401b301f  mov     r15, [rsp+0D8h+var_40]
0x1401b3027  mov     r12, [rsp+0D8h+var_38]
0x1401b302f  add     rsp, 0A8h
0x1401b3036  pop     r14
0x1401b3038  pop     r13
0x1401b303a  pop     rdi
0x1401b303b  pop     rsi
0x1401b303c  pop     rbp
0x1401b303d  pop     rbx
0x1401b303e  retn
0x1401b3040  mov     word ptr [r13+18h], 1000h
0x1401b3047  jmp     loc_1401B2EF1
0x1401b304c  lea     rsi, [rbp+90h]
0x1401b3053  mov     rcx, [r13+38h]
0x1401b3057  xor     edx, edx
0x1401b3059  add     rcx, 68h ; 'h'
0x1401b305d  call    cs:__imp_ExReleasePushLockEx
0x1401b3064  nop     dword ptr [rax+rax+00h]
0x1401b3069  mov     rcx, [r13+38h]; Resource
0x1401b306d  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1401b3074  nop     dword ptr [rax+rax+00h]
0x1401b3079  test    al, al
0x1401b307b  jnz     short loc_1401B30B3
0x1401b307d  mov     rcx, [r13+38h]; Resource
0x1401b3081  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401b3088  nop     dword ptr [rax+rax+00h]
0x1401b308d  test    eax, eax
0x1401b308f  jz      short loc_1401B30A1
0x1401b3091  mov     rcx, [r13+38h]; Resource
0x1401b3095  call    cs:__imp_ExReleaseResourceLite
0x1401b309c  nop     dword ptr [rax+rax+00h]
0x1401b30a1  mov     rcx, [r13+38h]; Resource
0x1401b30a5  mov     dl, 1; Wait
0x1401b30a7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401b30ae  nop     dword ptr [rax+rax+00h]
0x1401b30b3  movzx   r15d, [rsp+0D8h+arg_48]
0x1401b30bc  lea     rcx, [rsp+0D8h+Status]
0x1401b30c4  mov     r9d, [rsp+0D8h+arg_40]
0x1401b30cc  movzx   eax, r15b
0x1401b30d0  mov     [rsp+0D8h+var_B0], rcx
0x1401b30d5  and     al, 1
0x1401b30d7  mov     r8d, edi
0x1401b30da  mov     byte ptr [rsp+0D8h+Timeout], al
0x1401b30de  mov     rdx, r13
0x1401b30e1  mov     rcx, rbp
0x1401b30e4  call    LfsVerifyLogSpaceAvail
0x1401b30e9  mov     ecx, [rsp+0D8h+Status]; Status
0x1401b30f0  mov     [rsp+0D8h+var_8C], eax
0x1401b30f4  test    ecx, ecx
0x1401b30f6  jnz     loc_1401B396E
0x1401b30fc  movzx   ebx, word ptr [rbp+60h]
0x1401b3100  mov     rdx, [rsi]
0x1401b3103  add     ebx, edi
0x1401b3105  cmp     rdx, rsi
0x1401b3108  jz      short loc_1401B3118
0x1401b310a  mov     ecx, [rdx+18h]
0x1401b310d  sub     ecx, [rdx+28h]
0x1401b3110  cmp     ebx, ecx
0x1401b3112  ja      loc_1401B36CA
0x1401b3118  and     r15w, 2
0x1401b311d  mov     [rsp+0D8h+Status], ebx
0x1401b3124  mov     rax, [rsi]
0x1401b3127  cmp     rax, rsi
0x1401b312a  jz      loc_1401B350C
0x1401b3130  lea     r8, [rax-18h]
0x1401b3134  mov     ecx, [r8+30h]
0x1401b3138  sub     ecx, [r8+40h]
0x1401b313c  mov     r9d, [rbp+28h]
0x1401b3140  cmp     ecx, r9d
0x1401b3143  jb      short loc_1401B3152
0x1401b3145  xor     edx, edx
0x1401b3147  mov     eax, ecx
0x1401b3149  div     r9d
0x1401b314c  imul    eax, [rbp+50h]
0x1401b3150  sub     ecx, eax
0x1401b3152  cmp     ecx, ebx
0x1401b3154  jb      loc_1401B36BF
0x1401b315a  mov     r12, [rsi]
0x1401b315d  sub     r12, 18h
0x1401b3161  mov     [rsp+0D8h+var_90], edi
0x1401b3165  mov     r9d, [r12+40h]
0x1401b316a  mov     r8d, r9d
0x1401b316d  and     r8d, [rbp+2Ch]
0x1401b3171  jnz     loc_1401B32E6
0x1401b3177  mov     rax, [rbp+198h]
0x1401b317e  sub     [rbp+190h], rax
0x1401b3185  mov     eax, [rbp+50h]
0x1401b3188  add     [r12+40h], eax
0x1401b318d  mov     r9d, [r12+40h]
0x1401b3192  mov     r8d, [rbp+50h]
0x1401b3196  mov     byte ptr [rsp+0D8h+Status], 1
0x1401b319e  mov     eax, [rbp+28h]
0x1401b31a1  mov     ecx, [rbp+7Ch]
0x1401b31a4  sub     eax, r8d
0x1401b31a7  mov     rbx, [r12+38h]
0x1401b31ac  mov     dword ptr [rsp+0D8h+arg_8], eax
0x1401b31b3  mov     rax, [r12+28h]
0x1401b31b8  shl     rbx, cl
0x1401b31bb  mov     edx, r9d
0x1401b31be  sub     r9d, r8d
0x1401b31c1  add     rax, rdx
0x1401b31c4  mov     ecx, r9d
0x1401b31c7  shr     rax, 3
0x1401b31cb  add     rbx, rax
0x1401b31ce  mov     rax, [r12+48h]
0x1401b31d3  add     rcx, rax
0x1401b31d6  cmp     [rsp+0D8h+arg_20], 2
0x1401b31de  mov     [rsp+0D8h+var_A0], rcx
0x1401b31e3  lea     r15, [rax+rdx]
0x1401b31e7  jz      loc_1401B38FA
0x1401b31ed  movzx   r8d, word ptr [rbp+60h]; Size
0x1401b31f2  xor     edx, edx; Val
0x1401b31f4  mov     rcx, r15; void *
0x1401b31f7  call    memset
0x1401b31fc  mov     rax, [rsp+0D8h+arg_38]
0x1401b3204  mov     [r15+8], rax
0x1401b3208  mov     rax, [rsp+0D8h+arg_30]
0x1401b3210  mov     [r15+10h], rax
0x1401b3214  mov     rax, [rsp+0D8h+arg_28]
0x1401b321c  mov     [r15], rbx
0x1401b321f  test    rax, rax
0x1401b3222  jz      short loc_1401B322A
0x1401b3224  mov     eax, [rax]
0x1401b3226  mov     [r15+24h], eax
0x1401b322a  mov     [r15+18h], edi
0x1401b322e  mov     eax, [r13+20h]
0x1401b3232  mov     r13d, dword ptr [rsp+0D8h+arg_8]
0x1401b323a  mov     [r15+1Ch], eax
0x1401b323e  mov     eax, [rsp+0D8h+arg_20]
0x1401b3245  mov     [r15+20h], eax
  ... truncated ...
```
