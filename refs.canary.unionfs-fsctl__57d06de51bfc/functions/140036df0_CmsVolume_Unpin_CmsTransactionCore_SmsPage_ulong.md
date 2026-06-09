# CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)

- ea: `0x140036df0`
- end: `0x140037ab1`
- name: `?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z`
- size: `3265`
- prototype: `void __fastcall(CmsVolume *__hidden this, struct CmsTransactionCore *, struct SmsPage **, unsigned int)`
- caller_count: `168`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c4d4`
- `0x14000cf50`
- `0x14000e520`
- `0x140010b80`
- `0x140010d40`
- `0x1400132d0`
- `0x14001395c`
- `0x1400147f8`
- `0x140016a00`
- `0x140017c30`
- `0x14001a36c`
- `0x14001a680`
- `0x14001b120`
- `0x14001c6c0`
- `0x14001cd70`
- `0x14001d800`
- `0x14001d994`
- `0x14001e410`
- `0x140020ba8`
- `0x1400217c0`
- `0x1400228b0`
- `0x140023480`
- `0x140023c38`
- `0x140024710`
- `0x140024e04`
- `0x1400253bc`
- `0x140026350`
- `0x140027540`
- `0x140028670`
- `0x140028a20`
- `0x140029298`
- `0x140029ff0`
- `0x14002a3d0`
- `0x14002c4e0`
- `0x14002cef0`
- `0x14002d9b0`
- `0x14002e000`
- `0x140031cf0`
- `0x140031d40`
- `0x140033b60`
- `0x1400340e0`
- `0x140035300`
- `0x14003586c`
- `0x140035d20`
- `0x140036174`
- `0x140036860`
- `0x140036dd0`
- `0x14004a7c0`
- `0x14004b0a8`
- `0x14004b5c0`

## callees

- `0x140036df0`
- `0x140037ac0`
- `0x140037ae0`
- `0x140037af0`
- `0x140037b80`
- `0x140037bc0`
- `0x140056890`
- `0x14005a810`
- `0x14005a8a0`
- `0x14005c030`
- `0x14005c480`
- `0x1400989a0`
- `0x14009c920`
- `0x14009ceb0`
- `0x14012790c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14003753f`
- `ntoskrnl!KeSetEvent` at `0x1400377b6`
- `ntoskrnl!KeSetEvent` at `0x14003784f`
- `ntoskrnl!KeSetEvent` at `0x14003753f`
- `ntoskrnl!KeSetEvent` at `0x1400377b6`
- `ntoskrnl!KeSetEvent` at `0x14003784f`
- `ntoskrnl!KdDebuggerEnabled` at `0x14003723d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400374fb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400374fb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003790c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003790c`
- `ntoskrnl!ExDeleteFastResource` at `0x140037298`
- `ntoskrnl!ExDeleteFastResource` at `0x140037298`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003742a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003742a`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400375b6`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400375da`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400375fe`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140037622`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400375b6`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400375da`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400375fe`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140037622`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1f95`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1f95`
- `ntoskrnl!ExReleaseFastResource` at `0x140036efb`
- `ntoskrnl!ExReleaseFastResource` at `0x14003756e`
- `ntoskrnl!ExReleaseFastResource` at `0x140036efb`
- `ntoskrnl!ExReleaseFastResource` at `0x14003756e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400377da`
- `ntoskrnl!ExReleasePushLockEx` at `0x140037878`
- `ntoskrnl!ExReleasePushLockEx` at `0x140037956`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400377da`
- `ntoskrnl!ExReleasePushLockEx` at `0x140037878`
- `ntoskrnl!ExReleasePushLockEx` at `0x140037956`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037716`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037716`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a8f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140037768`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400377f9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140037768`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400377f9`

## pseudocode

```c
void __fastcall CmsVolume::Unpin(
        CmsVolumeContainer **this,
        struct CmsTransactionCore *a2,
        struct SmsPage **a3,
        unsigned int a4)
{
  struct SmsPage *v4; // r15
  struct SmsPage **v6; // rax
  __int16 v7; // di
  __int16 v8; // r14
  __int16 v9; // bx
  __int16 v10; // si
  struct SmsPage *v11; // rcx
  char *v12; // rcx
  __int64 v13; // r12
  int v14; // eax
  char *v15; // r12
  char *v16; // r8
  char *i; // rax
  bool v18; // zf
  __int64 v19; // rax
  signed __int32 v20; // eax
  CmsHashTable *v21; // r13
  unsigned __int64 v22; // r12
  int v23; // ecx
  struct SmsHashEntry *v24; // rax
  struct SmsHashEntry *v25; // r13
  __int64 v26; // rdx
  __int16 v27; // cx
  __int16 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // eax
  volatile __int64 *v33; // r12
  __int64 v34; // rax
  struct _MDL *v35; // rcx
  int v36; // r12d
  struct CmsTransactionCore *v37; // rdx
  __int64 v38; // rcx
  unsigned __int8 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r13
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  void *v46; // rcx
  struct SmsHashEntry *v47; // rax
  struct SmsHashEntry *v48; // r12
  __int64 v49; // rdx
  __int16 v50; // cx
  __int16 v51; // r8
  __int64 v52; // rcx
  __int64 v53; // rax
  int v54; // r8d
  __int64 v55; // r13
  __int64 v56; // rcx
  __int64 v57; // r15
  void *v58; // r12
  __int64 v59; // rcx
  __int64 v60; // r15
  struct _NPAGED_LOOKASIDE_LIST *v61; // rcx
  void *v62; // rdx
  _QWORD *v63; // r15
  _QWORD *v64; // rcx
  int v65; // eax
  __int64 v66; // rax
  int v67; // r9d
  int *v68; // r8
  int v69; // eax
  char **v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 *v73; // r13
  __int64 **v74; // rcx
  struct _KEVENT *v75; // rcx
  __int64 v76; // rax
  __int64 *v77; // r13
  __int64 **v78; // rcx
  struct _KEVENT *v79; // rcx
  _QWORD *v80; // rax
  char v81; // al
  __int64 v82; // rcx
  struct _SmsHashLocation *v83; // [rsp+38h] [rbp-C8h]
  struct SmsHashEntry **v84; // [rsp+40h] [rbp-C0h]
  char v85[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v86[12]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v87; // [rsp+68h] [rbp-98h]
  unsigned int v88; // [rsp+70h] [rbp-90h]
  __int64 v89; // [rsp+78h] [rbp-88h]
  _QWORD *v90; // [rsp+80h] [rbp-80h] BYREF
  struct SmsPage *v91; // [rsp+88h] [rbp-78h]
  __int128 v92; // [rsp+90h] [rbp-70h] BYREF
  __int64 v93; // [rsp+A0h] [rbp-60h]
  struct SmsPage *v94; // [rsp+A8h] [rbp-58h]
  __int128 v95; // [rsp+B0h] [rbp-50h]
  __int128 v96; // [rsp+D0h] [rbp-30h]
  __int128 v97; // [rsp+F0h] [rbp-10h] BYREF
  int v98; // [rsp+100h] [rbp+0h]
  int v99; // [rsp+104h] [rbp+4h]
  __int64 v100; // [rsp+108h] [rbp+8h]
  __int128 v101; // [rsp+110h] [rbp+10h] BYREF
  int v102; // [rsp+120h] [rbp+20h]
  int v103; // [rsp+124h] [rbp+24h]
  __int64 v104; // [rsp+128h] [rbp+28h]
  struct CmsTransactionCore *v106; // [rsp+178h] [rbp+78h]

  v106 = a2;
  v4 = *a3;
  v6 = a3;
  if ( *a3 )
  {
    v7 = *(_WORD *)&v86[10];
    v8 = *(_WORD *)&v86[10];
    v9 = *(_WORD *)&v86[10];
    v10 = *(_WORD *)&v86[10];
    while ( 1 )
    {
      v11 = (struct SmsPage *)*((_QWORD *)v4 + 38);
      v91 = 0;
      v88 = a4;
      if ( !v11 )
        goto LABEL_4;
      if ( (a4 & 1) != 0 && (v67 = *((_DWORD *)v4 + 78), *((_DWORD *)v4 + 96) == v67) )
      {
        v91 = v11;
        v68 = (int *)((char *)v4 + 316);
        if ( (a4 & 4) == 0 )
          goto LABEL_138;
        v69 = *v68;
        if ( *((_DWORD *)v4 + 97) != *v68 )
        {
          v88 = a4 & 0xFFFFFFFB;
          goto LABEL_138;
        }
      }
      else
      {
        if ( (a4 & 4) == 0 || (v68 = (int *)((char *)v4 + 316), v69 = *((_DWORD *)v4 + 79), *((_DWORD *)v4 + 97) != v69) )
        {
          a2 = v106;
          goto LABEL_4;
        }
        v67 = *((_DWORD *)v4 + 78);
        v91 = v11;
      }
      *v68 = v69 - 1;
LABEL_138:
      a2 = v106;
      *((_DWORD *)v4 + 78) = v67 - 1;
      if ( v67 == 1 )
        *((_QWORD *)v4 + 38) = 0;
LABEL_4:
      v12 = (char *)*((_QWORD *)v4 + 12);
      v85[0] = 122;
      v13 = *(_QWORD *)(*((_QWORD *)v12 + 4) + 40LL);
      v87 = v13;
      if ( (a4 & 4) != 0 )
        --*((_DWORD *)v4 + 97);
      if ( (a4 & 1) != 0 )
      {
        if ( v12[14] >= 0 )
          --*((_DWORD *)a2 + 49);
        v14 = *((_DWORD *)v4 + 96);
        if ( !v14 )
        {
          v15 = (char *)a2 + 664;
          v16 = (char *)v4 + 560;
          while ( v15 != (char *)a2 + 792 )
          {
            if ( *(char **)v15 == v16 )
              goto LABEL_17;
            v15 += 32;
          }
          v12 = (char *)a2 + 792;
          for ( i = (char *)*((_QWORD *)a2 + 99); i != v12; i = *(char **)i )
          {
            v15 = i - 16;
            if ( *((char **)i - 2) == v16 )
              goto LABEL_17;
          }
          v15 = 0;
LABEL_17:
          a2 = (struct CmsTransactionCore *)*((_QWORD *)v15 + 1);
          if ( a2 )
          {
            v18 = (*((_DWORD *)a2 + 18))-- == 1;
            if ( v18 )
            {
              *((_DWORD *)a2 + 19) &= ~2u;
              goto LABEL_20;
            }
          }
          else
          {
LABEL_20:
            ExReleaseFastResource((char *)v4 + 560, a2);
          }
          v19 = *((_QWORD *)v15 + 1);
          if ( !*(_DWORD *)(v19 + 72) )
          {
            a2 = (struct CmsTransactionCore *)*((_QWORD *)v15 + 2);
            v12 = v15 + 16;
            if ( a2 )
            {
              if ( *((char **)a2 + 1) != v12 || (v70 = (char **)*((_QWORD *)v15 + 3), *v70 != v12) )
LABEL_147:
                __fastfail(3u);
              *v70 = (char *)a2;
              *((_QWORD *)a2 + 1) = v70;
              v71 = *((_QWORD *)v15 + 1);
              if ( v71 )
                *(_DWORD *)(v71 + 76) &= ~1u;
              *((_QWORD *)v15 + 1) = 0;
              *(_QWORD *)v15 = 0;
              ExFreePoolWithTag(v15, 0);
            }
            else
            {
              if ( v19 )
                *(_DWORD *)(v19 + 76) &= ~1u;
              *((_QWORD *)v15 + 1) = 0;
              *(_QWORD *)v15 = 0;
            }
          }
          v13 = v87;
          goto LABEL_27;
        }
        v65 = v14 - 1;
        *((_DWORD *)v4 + 96) = v65;
        if ( !v65 )
          ExReleaseFastResource((char *)v4 + 560, 0);
      }
LABEL_27:
      if ( (a4 & 8) != 0 && !*((_QWORD *)v4 + 42) && (*((_DWORD *)v4 + 138) & 0x10) != 0 )
      {
        if ( *((_QWORD *)v4 + 16) )
          MmSetAddressRangeModified(*((PVOID *)v4 + 15), *((unsigned int *)v4 + 34));
        if ( *((_QWORD *)v4 + 20) )
          MmSetAddressRangeModified(*((PVOID *)v4 + 19), *((unsigned int *)v4 + 42));
        if ( *((_QWORD *)v4 + 24) )
          MmSetAddressRangeModified(*((PVOID *)v4 + 23), *((unsigned int *)v4 + 50));
        if ( *((_QWORD *)v4 + 28) )
          MmSetAddressRangeModified(*((PVOID *)v4 + 27), *((unsigned int *)v4 + 58));
        CmsVolume::CleanBackingPage((CmsVolume *)this, a2, v4);
        _InterlockedAnd((volatile signed __int32 *)v4 + 138, 0xFFFFFFEF);
      }
      if ( (a4 & 2) != 0 )
      {
        if ( (*((_DWORD *)v4 + 138) & 0x4000) != 0 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 95, 0xFFFFFFFF) == 1 )
          {
            *((_BYTE *)v4 + 393) = 1;
            v81 = 116;
          }
          else
          {
            v81 = 45;
          }
          v85[0] = v81;
        }
        else
        {
          while ( 1 )
          {
            v20 = *((_DWORD *)v4 + 95);
            if ( v20 <= 1 )
              break;
            if ( v20 == _InterlockedCompareExchange((volatile signed __int32 *)v4 + 95, v20 - 1, v20) )
              goto LABEL_32;
          }
          v21 = (CmsHashTable *)(v13 + 16);
          v22 = *(_QWORD *)v4;
          v23 = 9;
          v92 = 0;
          if ( (*(_DWORD *)v106 & 0x8000LL) != 0 )
            v23 = 1;
          v93 = 0;
          *(_DWORD *)&v86[8] = 0;
          LODWORD(v89) = v23;
          *(_QWORD *)v86 = v23 & 8;
          if ( (v23 & 8) != 0 )
            ExAcquirePushLockSharedEx((char *)v21 + 40, 4);
          v24 = CmsHashTable::FindAndLockEntryInternal(
                  v21,
                  v22,
                  0,
                  0,
                  *((_QWORD *)v21 + 2) != 0,
                  (struct _SmsHashLocation *)&v92,
                  (struct SmsHashEntry **)&v86[4],
                  v83,
                  v84);
          v25 = v24;
          if ( v24 )
          {
            v26 = *((_QWORD *)v24 + 1);
            v98 = 0;
            v97 = 0;
            v100 = 0;
            v27 = *(_WORD *)(v26 + 8);
            v28 = v27 & 3;
            if ( (v27 & 0x40) != 0 )
            {
              WORD2(v95) = v27 & 3;
              v31 = *(unsigned __int16 *)(v26 + 10);
              LODWORD(v95) = 12;
              WORD3(v95) = v7;
              *((_QWORD *)&v95 + 1) = v26 + 12;
            }
            else
            {
              v29 = *(unsigned __int16 *)(v26 + 10);
              LODWORD(v95) = *(unsigned __int16 *)(v26 + 6);
              v30 = v26 + *(unsigned __int16 *)(v26 + 4);
              WORD2(v95) = v28 | 4;
              v31 = *(_DWORD *)(v26 + 12);
              v26 += v29;
              *((_QWORD *)&v95 + 1) = v30;
              WORD3(v95) = v8;
            }
            v98 = v31;
            v100 = v26;
            v97 = v95;
            v99 = *(_DWORD *)&v86[8];
            v32 = DerefPageOrEnterTeardownState(v106, (struct _CmsRow *)&v97, v85);
            v33 = *(volatile __int64 **)&v86[4];
            if ( v32 == -1073741444 )
              CmsHashTable::DeleteInternal(v87 + 16, &v92, v25, *(_QWORD *)&v86[4], v89, 0);
            v34 = _InterlockedExchange64(v33, v92);
            *(_QWORD *)&v92 = 0;
            if ( v34 == -3 )
            {
              ExAcquirePushLockExclusiveEx(&qword_1402653F0, 0);
              v72 = qword_1402653F8;
              if ( (__int64 *)qword_1402653F8 != &qword_1402653F8 )
              {
                do
                {
                  v73 = *(__int64 **)v72;
                  if ( *(volatile __int64 **)(v72 + 24) == v33 )
                  {
                    if ( v73[1] != v72 )
                      goto LABEL_147;
                    v74 = *(__int64 ***)(v72 + 8);
                    if ( *v74 != (__int64 *)v72 )
                      goto LABEL_147;
                    *v74 = v73;
                    v73[1] = (__int64)v74;
                    v75 = *(struct _KEVENT **)(v72 + 16);
                    *(_QWORD *)v72 = 0;
                    KeSetEvent(v75, 0, 0);
                  }
                  v72 = (__int64)v73;
                }
                while ( v73 != &qword_1402653F8 );
              }
              ExReleasePushLockEx(&qword_1402653F0, 0);
            }
          }
          if ( *(_DWORD *)v86 )
            ExReleasePushLockEx(v87 + 56, 0);
        }
        if ( v85[0] == 116 )
        {
          if ( !*((_QWORD *)v4 + 42) && (*((_DWORD *)v4 + 138) & 0x10) != 0 )
            CmsVolume::CleanInternalBeforeUnmap((CmsVolume *)v12, a2, v4);
          v35 = (struct _MDL *)*((_QWORD *)v4 + 84);
          if ( v35 )
          {
            MsKmeUnlockPages(v35);
            *((_QWORD *)v4 + 84) = 0;
          }
          _InterlockedAnd((volatile signed __int32 *)v4 + 138, 0xFFFFFFFB);
          v36 = 0;
          CmsChecksum::GenerateChecksum(*((_QWORD *)v4 + 13), (char *)v4 + 120);
          if ( *((_QWORD *)v4 + 16) )
          {
            ((void (*)(void))MsKmeUnpinData)();
            v36 = 1;
            *((_QWORD *)v4 + 16) = 0;
            *((_QWORD *)v4 + 15) = 0;
          }
          if ( *((_QWORD *)v4 + 20) )
          {
            ((void (*)(void))MsKmeUnpinData)();
            *((_QWORD *)v4 + 20) = 0;
            ++v36;
            *((_QWORD *)v4 + 19) = 0;
          }
          if ( *((_QWORD *)v4 + 24) )
          {
            ((void (*)(void))MsKmeUnpinData)();
            *((_QWORD *)v4 + 24) = 0;
            ++v36;
            *((_QWORD *)v4 + 23) = 0;
          }
          if ( *((_QWORD *)v4 + 28) )
          {
            ((void (*)(void))MsKmeUnpinData)();
            *((_QWORD *)v4 + 28) = 0;
            ++v36;
            *((_QWORD *)v4 + 27) = 0;
          }
          if ( v36 )
          {
            _InterlockedAnd((volatile signed __int32 *)v4 + 138, 0xFFFFFFFD);
            MsKmeFreeBaseAddressFromTuple(
              *((void **)v4 + 13),
              *((void **)v4 + 14),
              (struct SmsPage *)((char *)v4 + 120));
            *((_QWORD *)v4 + 13) = 0;
            *((_QWORD *)v4 + 14) = 0;
            _InterlockedDecrement((volatile signed __int32 *)&DbgCounts);
          }
          if ( !*((_QWORD *)v4 + 42) && (*((_DWORD *)v4 + 138) & 0x10) != 0 )
          {
            CmsVolume::CleanBackingPage((CmsVolume *)this, v37, v4);
            _InterlockedAnd((volatile signed __int32 *)v4 + 138, 0xFFFFFFEF);
          }
          if ( (*((_DWORD *)v4 + 138) & 0x80u) != 0 )
          {
            v38 = *((_QWORD *)v4 + 12);
            v39 = (*(_BYTE *)(v38 + 14) & 0x40) != 0 || (*(_DWORD *)(*(_QWORD *)(v38 + 24) + 44LL) & 0x80u) != 0;
            MspDeductDirtyPageCount((struct CmsVolume *)this, *((_DWORD *)v4 + 94), v39);
            _InterlockedAnd((volatile signed __int32 *)v4 + 138, 0xFFFFFF7F);
          }
          if ( byte_140261FDB )
            CmsVolume::TrimPage((CmsVolume *)this, v37, v4);
          v40 = *((unsigned int *)v4 + 138);
          if ( (v40 & 0x40) != 0 )
          {
            CmsVolumeContainer::SetContainerStationaryVolatile(this[417], v106, v4, 0, 0);
            v40 = *((unsigned int *)v4 + 138);
          }
          v41 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 12) + 32LL) + 40LL);
          if ( (_BYTE)KdDebuggerEnabled && (v40 & 0x3000) != 0 )
            __debugbreak();
          v42 = *((_QWORD *)v4 + 16);
          if ( v42 )
          {
            MsKmeUnpinData(v42, v40);
            *((_QWORD *)v4 + 16) = 0;
            *((_QWORD *)v4 + 15) = 0;
            *((_DWORD *)v4 + 34) = 0;
          }
          v43 = *((_QWORD *)v4 + 20);
          if ( v43 )
          {
            MsKmeUnpinData(v43, v40);
            *((_QWORD *)v4 + 20) = 0;
            *((_QWORD *)v4 + 19) = 0;
            *((_DWORD *)v4 + 42) = 0;
          }
          v44 = *((_QWORD *)v4 + 24);
          if ( v44 )
          {
            MsKmeUnpinData(v44, v40);
            *((_QWORD *)v4 + 24) = 0;
            *((_QWORD *)v4 + 23) = 0;
            *((_DWORD *)v4 + 50) = 0;
          }
          v45 = *((_QWORD *)v4 + 28);
          if ( v45 )
          {
            MsKmeUnpinData(v45, v40);
            *((_QWORD *)v4 + 28) = 0;
            *((_QWORD *)v4 + 27) = 0;
            *((_DWORD *)v4 + 58) = 0;
          }
          ExDeleteFastResource((char *)v4 + 560);
          v46 = (void *)*((_QWORD *)v4 + 35);
          if ( v46 != (void *)-1LL )
          {
            *((_QWORD *)v4 + 36) = v46;
            if ( v46 )
              ExFreePoolWithTag(v46, 0);
          }
          v18 = (*((_DWORD *)v4 + 138) & 0x4000) == 0;
          v92 = 0;
          v90 = 0;
          if ( v18 )
          {
            *(_QWORD *)&v86[4] = 0;
            v18 = *(_QWORD *)(v41 + 32) == 0;
            v93 = 0;
            v89 = v41 + 16;
            v47 = CmsHashTable::FindAndLockEntryInternal(
                    (CmsHashTable *)(v41 + 16),
                    *(_QWORD *)v4,
                    0,
                    0,
                    !v18,
                    (struct _SmsHashLocation *)&v92,
                    (struct SmsHashEntry **)&v86[4],
                    v83,
                    v84);
            v48 = v47;
            if ( v47 )
            {
              v49 = *((_QWORD *)v47 + 1);
              v102 = 0;
              v101 = 0;
              v104 = 0;
              v50 = *(_WORD *)(v49 + 8);
              v51 = v50 & 3;
              if ( (v50 & 0x40) != 0 )
              {
                WORD2(v96) = v50 & 3;
                v54 = *(unsigned __int16 *)(v49 + 10);
                LODWORD(v96) = 12;
                WORD3(v96) = v9;
                *((_QWORD *)&v96 + 1) = v49 + 12;
              }
              else
              {
                v52 = *(unsigned __int16 *)(v49 + 10);
                LODWORD(v96) = *(unsigned __int16 *)(v49 + 6);
                v53 = v49 + *(unsigned __int16 *)(v49 + 4);
                WORD2(v96) = v51 | 4;
                v54 = *(_DWORD *)(v49 + 12);
                v49 += v52;
                *((_QWORD *)&v96 + 1) = v53;
                WORD3(v96) = v10;
              }
              v102 = v54;
              v104 = v49;
              v101 = v96;
              v103 = *(_DWORD *)&v86[8];
              if ( !(unsigned int)DequeueTeardownWaiters(v106, &v101, &v90) )
              {
                v55 = *((_QWORD *)v48 + 1);
                v56 = v92;
                v57 = *(_QWORD *)&v86[4];
                v87 = v55;
                *((_QWORD *)v48 + 1) = 0;
                if ( v56 == -1 )
                {
                  *(_QWORD *)v48 = 0;
                  v66 = *(_QWORD *)(v57 + 8);
                  v18 = (*(_DWORD *)(v66 + 4))-- == 1;
                  if ( v18 )
                  {
                    v58 = *(void **)(v57 + 8);
                    v56 = 0;
                    *(_QWORD *)(v57 + 8) = 0;
                  }
                  else
                  {
                    v58 = 0;
                  }
                }
                else
                {
                  v56 = 0;
                  v58 = 0;
                }
                v59 = _InterlockedExchange64((volatile __int64 *)v57, v56);
                *(_QWORD *)&v92 = 0;
                if ( v59 == -3 )
                {
                  ExAcquirePushLockExclusiveEx(&qword_1402653F0, 0);
                  v76 = qword_1402653F8;
                  if ( (__int64 *)qword_1402653F8 != &qword_1402653F8 )
                  {
                    do
                    {
                      v77 = *(__int64 **)v76;
                      if ( *(_QWORD *)(v76 + 24) == v57 )
                      {
                        if ( v77[1] != v76 )
                          goto LABEL_147;
                        v78 = *(__int64 ***)(v76 + 8);
                        if ( *v78 != (__int64 *)v76 )
                          goto LABEL_147;
                        *v78 = v77;
                        v77[1] = (__int64)v78;
                        v79 = *(struct _KEVENT **)(v76 + 16);
                        *(_QWORD *)v76 = 0;
                        KeSetEvent(v79, 0, 0);
                      }
                      v76 = (__int64)v77;
                    }
                    while ( v77 != &qword_1402653F8 );
                    v55 = v87;
                  }
                  ExReleasePushLockEx(&qword_1402653F0, 0);
                }
                if ( v55 )
                {
                  v60 = *(_QWORD *)(v55 - 16);
                  if ( v60 )
                  {
                    if ( *(_BYTE *)(v60 + 8) )
                    {
                      v61 = (struct _NPAGED_LOOKASIDE_LIST *)(v60 + 64);
                      v62 = (void *)(v55 - 16);
                      if ( *(_BYTE *)(v60 + 9) )
                        ExFreeToNPagedLookasideList(v61, v62);
                      else
                        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v61, v62);
                      goto LABEL_103;
                    }
                    v82 = *(_QWORD *)(v60 + 88);
                    if ( (int)v82 < *(_DWORD *)(v60 + 80) || SHIDWORD(v82) >= (int)v82 )
                    {
                      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v60 + 64), (PSLIST_ENTRY)(v55 - 16));
                      _InterlockedIncrement((volatile signed __int32 *)(v60 + 88));
                      goto LABEL_103;
                    }
                  }
                  ExFreePoolWithTag((PVOID)(v55 - 16), 0);
                }
LABEL_103:
                if ( v58 )
                  ExFreePoolWithTag(v58, 0);
                _InterlockedDecrement((volatile signed __int32 *)(16LL * DWORD2(v92) + v89 + 12));
              }
            }
          }
          else
          {
            v80 = (_QWORD *)*((_QWORD *)v4 + 8);
            *((_QWORD *)v4 + 8) = 0;
            v90 = v80;
            LODWORD(v93) = 0;
            v94 = v4;
            CmsHashTable::FreeIndexEntry((struct SmsPage *)((char *)v4 - 16));
          }
          v63 = v90;
          while ( v63 )
          {
            v64 = v63;
            v63 = (_QWORD *)*v63;
            KeSetEvent((PRKEVENT)(v64 + 1), 0, 0);
          }
        }
      }
LABEL_32:
      if ( !v91 )
      {
        v6 = a3;
        break;
      }
      a4 = v88;
      v4 = v91;
      a2 = v106;
    }
  }
  *v6 = 0;
}

```

## disassembly

```asm
0x140036df0  mov     [rsp-8+arg_18], rbx
0x140036df5  mov     [rsp-8+arg_10], r8
0x140036dfa  mov     [rsp-8+arg_8], rdx
0x140036dff  mov     [rsp-8+arg_0], rcx
0x140036e04  push    rbp
0x140036e05  push    rsi
0x140036e06  push    rdi
0x140036e07  push    r12
0x140036e09  push    r13
0x140036e0b  push    r14
0x140036e0d  push    r15
0x140036e0f  lea     rbp, [rsp-30h]
0x140036e14  sub     rsp, 130h
0x140036e1b  mov     r15, [r8]
0x140036e1e  xor     r10d, r10d
0x140036e21  mov     r13d, r9d
0x140036e24  mov     rax, r8
0x140036e27  test    r15, r15
0x140036e2a  jz      loc_140036F93
0x140036e30  movzx   edi, word ptr [rsp+160h+var_108+6]
0x140036e35  movzx   r14d, word ptr [rsp+160h+var_108+6]
0x140036e3b  movzx   ebx, word ptr [rsp+160h+var_108+6]
0x140036e40  movzx   esi, word ptr [rsp+160h+var_108+6]
0x140036e45  mov     rcx, [r15+130h]
0x140036e4c  mov     [rbp+60h+var_D8], r10
0x140036e50  mov     [rsp+160h+var_F0], r13d
0x140036e55  test    rcx, rcx
0x140036e58  jnz     loc_1400376A0
0x140036e5e  mov     rcx, [r15+60h]
0x140036e62  mov     [rsp+160h+var_110], 7Ah ; 'z'
0x140036e67  mov     rax, [rcx+20h]
0x140036e6b  mov     r12, [rax+28h]
0x140036e6f  mov     [rsp+160h+var_F8], r12
0x140036e74  test    r13b, 4
0x140036e78  jnz     loc_14003743B
0x140036e7e  test    r13b, 1
0x140036e82  jz      loc_140036F3F
0x140036e88  cmp     byte ptr [rcx+0Eh], 0
0x140036e8c  jl      short loc_140036E94
0x140036e8e  dec     dword ptr [rdx+0C4h]
0x140036e94  mov     eax, [r15+180h]
0x140036e9b  test    eax, eax
0x140036e9d  jnz     loc_140037555
0x140036ea3  lea     r12, [rdx+298h]
0x140036eaa  lea     rax, [r12+80h]
0x140036eb2  lea     r8, [r15+230h]
0x140036eb9  cmp     r12, rax
0x140036ebc  jz      short loc_140036ECA
0x140036ebe  cmp     [r12], r8
0x140036ec2  jz      short loc_140036EE0
0x140036ec4  add     r12, 20h ; ' '
0x140036ec8  jmp     short loc_140036EB9
0x140036eca  lea     rcx, [rdx+318h]
0x140036ed1  mov     rax, [rcx]
0x140036ed4  cmp     rax, rcx
0x140036ed7  jnz     loc_1400374E5
0x140036edd  mov     r12, r10
0x140036ee0  mov     rdx, [r12+8]
0x140036ee5  test    rdx, rdx
0x140036ee8  jz      loc_14003757F
0x140036eee  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x140036ef2  jnz     short loc_140036F0A
0x140036ef4  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x140036ef8  mov     rcx, r8
0x140036efb  call    cs:__imp_ExReleaseFastResource
0x140036f02  nop     dword ptr [rax+rax+00h]
0x140036f07  xor     r10d, r10d
0x140036f0a  mov     rax, [r12+8]
0x140036f0f  cmp     dword ptr [rax+48h], 0
0x140036f13  jnz     short loc_140036F3A
0x140036f15  mov     rdx, [r12+10h]
0x140036f1a  lea     rcx, [r12+10h]
0x140036f1f  test    rdx, rdx
0x140036f22  jnz     loc_1400376DC
0x140036f28  test    rax, rax
0x140036f2b  jz      short loc_140036F31
0x140036f2d  and     dword ptr [rax+4Ch], 0FFFFFFFEh
0x140036f31  mov     [r12+8], r10
0x140036f36  mov     [r12], r10
0x140036f3a  mov     r12, [rsp+160h+var_F8]
0x140036f3f  test    r13b, 8
0x140036f43  jnz     loc_140037584
0x140036f49  test    r13b, 2
0x140036f4d  jz      short loc_140036F7C
0x140036f4f  test    dword ptr [r15+228h], 4000h
0x140036f5a  jnz     loc_1400378DC
0x140036f60  mov     eax, [r15+17Ch]
0x140036f67  cmp     eax, 1
0x140036f6a  jle     short loc_140036FB2
0x140036f6c  nop
0x140036f6d  lea     ecx, [rax-1]
0x140036f70  lock cmpxchg [r15+17Ch], ecx
0x140036f79  nop
0x140036f7a  jnz     short loc_140036F60
0x140036f7c  mov     rax, [rbp+60h+var_D8]
0x140036f80  xor     r10d, r10d
0x140036f83  test    rax, rax
0x140036f86  jnz     loc_140037AA0
0x140036f8c  mov     rax, [rbp+60h+arg_10]
0x140036f93  mov     rbx, [rsp+160h+arg_18]
0x140036f9b  mov     [rax], r10
0x140036f9e  add     rsp, 130h
0x140036fa5  pop     r15
0x140036fa7  pop     r14
0x140036fa9  pop     r13
0x140036fab  pop     r12
0x140036fad  pop     rdi
0x140036fae  pop     rsi
0x140036faf  pop     rbp
0x140036fb0  retn
0x140036fb2  mov     rax, [rbp+60h+arg_8]
0x140036fb6  lea     r13, [r12+10h]
0x140036fbb  mov     r12, [r15]
0x140036fbe  mov     ecx, 9
0x140036fc3  xorps   xmm0, xmm0
0x140036fc6  movups  [rbp+60h+var_D0], xmm0
0x140036fca  mov     eax, [rax]
0x140036fcc  bt      rax, 0Fh
0x140036fd1  mov     eax, 1
0x140036fd6  cmovb   ecx, eax
0x140036fd9  xor     eax, eax
0x140036fdb  mov     [rbp+60h+var_C0], rax
0x140036fdf  mov     [rsp+58h], rax
0x140036fe4  mov     eax, ecx
0x140036fe6  and     eax, 8
0x140036fe9  mov     dword ptr [rsp+160h+var_E8], ecx
0x140036fed  mov     [rsp+160h+var_10C], eax
0x140036ff1  jnz     loc_140037903
0x140036ff7  cmp     qword ptr [r13+10h], 0
0x140036ffc  lea     rcx, [rsp+160h+var_108]
0x140037001  mov     [rsp+160h+var_130], rcx; struct SmsHashEntry **
0x140037006  mov     rdx, r12; unsigned __int64
0x140037009  setnz   al
0x14003700c  lea     rcx, [rbp+60h+var_D0]
0x140037010  mov     [rsp+160h+var_138], rcx; struct _SmsHashLocation *
0x140037015  xor     r9d, r9d; unsigned __int8
0x140037018  mov     rcx, r13; this
0x14003701b  mov     byte ptr [rsp+160h+var_140], al; char
0x14003701f  xor     r8d, r8d; unsigned __int8
0x140037022  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x140037027  mov     r13, rax
0x14003702a  test    rax, rax
0x14003702d  jz      loc_1400370DF
0x140037033  mov     rdx, [r13+8]
0x140037037  xor     eax, eax
0x140037039  xorps   xmm0, xmm0
0x14003703c  mov     [rbp+60h+var_60], eax
0x14003703f  movups  [rbp+60h+var_70], xmm0
0x140037043  mov     [rbp+60h+var_58], rax
0x140037047  movzx   ecx, word ptr [rdx+8]
0x14003704b  lea     r9, [rdx+0Ch]
0x14003704f  movzx   r8d, cx
0x140037053  and     r8w, 3
0x140037058  test    cl, 40h
0x14003705b  jnz     loc_14003764A
0x140037061  movzx   eax, word ptr [rdx+6]
0x140037065  or      r8w, 4
0x14003706a  movzx   ecx, word ptr [rdx+0Ah]
0x14003706e  mov     dword ptr [rbp+60h+var_B0], eax
0x140037071  movzx   eax, word ptr [rdx+4]
0x140037075  add     rax, rdx
0x140037078  mov     word ptr [rbp+60h+var_B0+4], r8w
0x14003707d  mov     r8d, [r9]
0x140037080  add     rdx, rcx
0x140037083  mov     qword ptr [rbp+60h+var_B0+8], rax
0x140037087  mov     word ptr [rbp+60h+var_B0+6], r14w
0x14003708c  movups  xmm0, [rbp+60h+var_B0]
0x140037090  mov     eax, [rsp+5Ch]
0x140037094  mov     rcx, [rbp+60h+arg_8]; struct CmsTransactionCore *
0x140037098  mov     [rbp+60h+var_60], r8d
0x14003709c  lea     r8, [rsp+160h+var_110]; void *
0x1400370a1  mov     [rbp+60h+var_58], rdx
0x1400370a5  lea     rdx, [rbp+60h+var_70]; struct _CmsRow *
0x1400370a9  movups  [rbp+60h+var_70], xmm0
0x1400370ad  mov     [rbp+60h+var_5C], eax
0x1400370b0  call    ?DerefPageOrEnterTeardownState@@YAJPEAVCmsTransactionCore@@PEAU_CmsRow@@PEAX@Z; DerefPageOrEnterTeardownState(CmsTransactionCore *,_CmsRow *,void *)
0x1400370b5  mov     r12, [rsp+160h+var_108]
0x1400370ba  cmp     eax, 0C000017Ch
0x1400370bf  jz      loc_14003791D
0x1400370c5  mov     rax, qword ptr [rbp+60h+var_D0]
0x1400370c9  xchg    rax, [r12]
0x1400370cd  mov     qword ptr [rbp+60h+var_D0], 0
0x1400370d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400370d9  jz      loc_14003775F
0x1400370df  cmp     [rsp+160h+var_10C], 0
0x1400370e4  jnz     loc_14003794B
0x1400370ea  cmp     [rsp+160h+var_110], 74h ; 't'
0x1400370ef  jnz     loc_140036F7C
0x1400370f5  cmp     qword ptr [r15+150h], 0
0x1400370fd  jnz     short loc_14003710E
0x1400370ff  mov     eax, [r15+228h]
0x140037106  test    al, 10h
0x140037108  jnz     loc_140037967
0x14003710e  mov     rcx, [r15+2A0h]; Mdl
0x140037115  test    rcx, rcx
0x140037118  jz      short loc_14003712A
0x14003711a  call    ?MsKmeUnlockPages@@YAXPEAX@Z; MsKmeUnlockPages(void *)
0x14003711f  mov     qword ptr [r15+2A0h], 0
0x14003712a  nop
0x14003712b  lock and dword ptr [r15+228h], 0FFFFFFFBh
0x140037134  nop
0x140037135  lea     rdx, [r15+78h]
0x140037139  mov     rcx, [r15+68h]
0x14003713d  xor     r12d, r12d
0x140037140  call    ?GenerateChecksum@CmsChecksum@@UEBAXV?$span@$$CBW4byte@utl@@$0?0@utl@@V?$span@W4byte@utl@@$0?0@3@@Z; CmsChecksum::GenerateChecksum(utl::span<utl::byte const,-1>,utl::span<utl::byte,-1>)
0x140037145  mov     rcx, [r15+80h]
0x14003714c  test    rcx, rcx
0x14003714f  jnz     loc_140037447
0x140037155  mov     rcx, [r15+0A0h]
0x14003715c  test    rcx, rcx
0x14003715f  jnz     loc_140037464
0x140037165  mov     rcx, [r15+0C0h]
0x14003716c  test    rcx, rcx
0x14003716f  jnz     loc_140037481
0x140037175  mov     rcx, [r15+0E0h]
0x14003717c  test    rcx, rcx
0x14003717f  jnz     loc_14003749E
0x140037185  test    r12d, r12d
0x140037188  jz      loc_140037974
0x14003718e  nop
0x14003718f  lock and dword ptr [r15+228h], 0FFFFFFFDh
0x140037198  nop
0x140037199  lea     r8, [r15+78h]; struct _MS_CC_DATA_TUPLE *
0x14003719d  mov     rdx, [r15+70h]; void *
0x1400371a1  mov     rcx, [r15+68h]; void *
0x1400371a5  call    ?MsKmeFreeBaseAddressFromTuple@@YAXPEAX0PEAU_MS_CC_DATA_TUPLE@@@Z; MsKmeFreeBaseAddressFromTuple(void *,void *,_MS_CC_DATA_TUPLE *)
0x1400371aa  xor     r12d, r12d
0x1400371ad  mov     [r15+68h], r12
0x1400371b1  mov     [r15+70h], r12
0x1400371b5  nop
0x1400371b6  lock dec cs:?DbgCounts@@3U_SmsDebugCounts@@A; _SmsDebugCounts DbgCounts
0x1400371bd  nop
0x1400371be  cmp     qword ptr [r15+150h], 0
0x1400371c6  mov     r13, [rbp+60h+arg_0]
0x1400371ca  jz      loc_1400374BB
0x1400371d0  mov     eax, [r15+228h]
0x1400371d7  test    al, al
0x1400371d9  jns     short loc_140037218
0x1400371db  mov     rcx, [r15+60h]
0x1400371df  test    byte ptr [rcx+0Eh], 40h
0x1400371e3  jnz     loc_14003797C
0x1400371e9  mov     rax, [rcx+18h]
0x1400371ed  mov     ecx, [rax+2Ch]
0x1400371f0  test    cl, cl
0x1400371f2  js      loc_14003797C
0x1400371f8  xor     r8b, r8b; unsigned __int8
0x1400371fb  mov     edx, [r15+178h]; int
0x140037202  mov     rcx, r13; struct CmsVolume *
0x140037205  call    ?MspDeductDirtyPageCount@@YAXPEAVCmsVolume@@JE@Z; MspDeductDirtyPageCount(CmsVolume *,long,uchar)
0x14003720a  nop
0x14003720b  lock and dword ptr [r15+228h], 0FFFFFF7Fh
0x140037217  nop
0x140037218  cmp     cs:byte_140261FDB, 0
0x14003721f  jnz     loc_140037984
0x140037225  mov     edx, [r15+228h]
0x14003722c  test    dl, 40h
0x14003722f  jnz     loc_140037994
0x140037235  mov     rax, [r15+60h]
0x140037239  mov     rcx, [rax+20h]
0x14003723d  mov     rax, cs:KdDebuggerEnabled
0x140037244  mov     r13, [rcx+28h]
0x140037248  cmp     byte ptr [rax], 0
0x14003724b  jnz     loc_1400379BB
0x140037251  mov     rcx, [r15+80h]
0x140037258  test    rcx, rcx
0x14003725b  jnz     loc_1400379CD
0x140037261  mov     rcx, [r15+0A0h]
0x140037268  test    rcx, rcx
0x14003726b  jnz     loc_1400379E9
0x140037271  mov     rcx, [r15+0C0h]
0x140037278  test    rcx, rcx
0x14003727b  jnz     loc_140037A08
0x140037281  mov     rcx, [r15+0E0h]
0x140037288  test    rcx, rcx
0x14003728b  jnz     loc_140037A27
0x140037291  lea     rcx, [r15+230h]
0x140037298  call    cs:__imp_ExDeleteFastResource
0x14003729f  nop     dword ptr [rax+rax+00h]
0x1400372a4  mov     rcx, [r15+118h]; P
0x1400372ab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400372af  jz      short loc_1400372CB
0x1400372b1  mov     [r15+120h], rcx
0x1400372b8  test    rcx, rcx
0x1400372bb  jz      short loc_1400372CB
0x1400372bd  xor     edx, edx; Tag
0x1400372bf  call    cs:__imp_ExFreePoolWithTag
0x1400372c6  nop     dword ptr [rax+rax+00h]
0x1400372cb  test    dword ptr [r15+228h], 4000h
0x1400372d6  xorps   xmm0, xmm0
0x1400372d9  movups  [rbp+60h+var_D0], xmm0
0x1400372dd  mov     [rbp+60h+var_E0], r12
0x1400372e1  jnz     loc_140037889
0x1400372e7  xor     eax, eax
0x1400372e9  mov     [rsp+160h+var_108], r12
0x1400372ee  cmp     [r13+20h], rax
0x1400372f2  lea     rcx, [r13+10h]; this
0x1400372f6  lea     rdx, [rsp+160h+var_108]
0x1400372fb  mov     [rbp+60h+var_C0], rax
0x1400372ff  mov     [rsp+160h+var_130], rdx; struct SmsHashEntry **
0x140037304  setnz   al
  ... truncated ...
```
