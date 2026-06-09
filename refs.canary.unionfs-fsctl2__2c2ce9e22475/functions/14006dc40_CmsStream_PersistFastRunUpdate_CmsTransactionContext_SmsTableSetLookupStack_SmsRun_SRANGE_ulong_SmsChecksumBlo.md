# CmsStream::PersistFastRunUpdate(CmsTransactionContext *,SmsTableSetLookupStack *,SmsRun *,_SRANGE *,ulong,SmsChecksumBlob *,ulong)

- ea: `0x14006dc40`
- end: `0x14006e2de`
- name: `?PersistFastRunUpdate@CmsStream@@AEAAJPEAVCmsTransactionContext@@PEAUSmsTableSetLookupStack@@PEAUSmsRun@@PEAU_SRANGE@@KPEAUSmsChecksumBlob@@K@Z`
- size: `1694`
- prototype: `int(CmsStream *__hidden this, struct CmsTransactionContext *, struct SmsTableSetLookupStack *, struct SmsRun *, struct _SRANGE *, unsigned int, struct SmsChecksumBlob *, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002a3d0`

## callees

- `0x140016300`
- `0x14001a0c0`
- `0x14001f1a0`
- `0x1400260b4`
- `0x140027400`
- `0x140027ee8`
- `0x140028670`
- `0x140029a90`
- `0x14006d634`
- `0x14006dc40`
- `0x14006e2f0`
- `0x140083ec0`
- `0x1400a7b90`
- `0x1400ac160`
- `0x1400b67d8`
- `0x1400c3a64`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1400cc9fc`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14006e1d0`
- `ntoskrnl!KdDebuggerEnabled` at `0x14006e1f6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e24b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006e24b`
- `ntoskrnl!ExAllocatePool2` at `0x14006dda4`
- `ntoskrnl!ExAllocatePool2` at `0x14006dda4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006dd69`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006dd69`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6739`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6739`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e268`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006e268`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14006e077`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14006e077`

## string_xrefs

- `0x14006ddbb`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsStream::PersistFastRunUpdate(
        CmsStream *this,
        struct CmsTransactionContext *a2,
        struct SmsTableSetLookupStack *a3,
        struct SmsRun *a4,
        struct _SRANGE *a5,
        unsigned int a6,
        struct SmsChecksumBlob *a7,
        unsigned int a8)
{
  __int16 v8; // di
  CmsStream *v9; // r14
  struct SmsChecksumBlob *v10; // r12
  __int64 v11; // xmm0_8
  struct CmsTransactionContext *v12; // r13
  __int64 v13; // rdx
  __int64 v15; // r8
  struct SmsRun *v16; // rsi
  _QWORD *v17; // r9
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // r12
  char *v21; // r15
  int v22; // edx
  unsigned int *v23; // r14
  unsigned int v24; // ecx
  unsigned int v25; // r13d
  unsigned __int64 v26; // rbx
  unsigned int *v27; // rdi
  unsigned __int64 v28; // rdx
  __int64 Pool2; // rax
  _DWORD *v30; // rbx
  int v31; // ecx
  _QWORD *v32; // rdi
  unsigned int v33; // eax
  __int64 v34; // r9
  unsigned int v35; // eax
  _QWORD *v36; // rcx
  __int64 v37; // r10
  _QWORD *v38; // r9
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  int inserted; // edx
  char v42; // bl
  __int16 v43; // ax
  __int64 v45; // r14
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r10
  int v49; // r11d
  __int64 v50; // rax
  char *v51; // r9
  size_t ChecksumLength; // rax
  __int64 v53; // r9
  unsigned __int64 v54; // rdx
  __int64 v55; // rax
  _QWORD *v56; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v57; // rcx
  _DWORD *v58; // rax
  _QWORD *v59; // rcx
  __int64 v60; // rax
  __int64 v61; // xmm1_8
  __int64 v62; // r10
  __int128 v63; // xmm0
  int v64; // ecx
  __int64 v65; // r8
  unsigned __int16 ChecksumSizeInBytes; // ax
  __int64 v67; // r8
  __int64 v68; // rcx
  __int64 v69; // rdi
  unsigned int v70; // ecx
  const struct SmsRun *v71; // r11
  __int64 v72; // r8
  __int64 v73; // rbx
  int v74; // edi
  char ChecksumType; // bl
  const struct CmsVolume *v76; // rdx
  unsigned __int16 v77; // ax
  unsigned int v78; // r9d
  CmsBPlusTable *v79; // rbx
  unsigned int v80; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+28h] [rbp-D8h]
  unsigned int v82[2]; // [rsp+30h] [rbp-D0h]
  int v83; // [rsp+38h] [rbp-C8h]
  char v84; // [rsp+38h] [rbp-C8h]
  struct SmsRun *v85; // [rsp+40h] [rbp-C0h]
  unsigned int v86; // [rsp+48h] [rbp-B8h]
  __int16 v87; // [rsp+60h] [rbp-A0h]
  __int16 v88; // [rsp+62h] [rbp-9Eh]
  __int64 v89; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v90; // [rsp+70h] [rbp-90h]
  __int64 v91; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v92[24]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v93; // [rsp+98h] [rbp-68h]
  __int64 v94; // [rsp+A0h] [rbp-60h]
  _QWORD v95[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v96; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v97; // [rsp+BCh] [rbp-44h]
  __int16 v98; // [rsp+BEh] [rbp-42h]
  _BYTE *v99; // [rsp+C0h] [rbp-40h]
  int v100; // [rsp+C8h] [rbp-38h]
  int v101; // [rsp+CCh] [rbp-34h]
  _BYTE *v102; // [rsp+D0h] [rbp-30h]
  _QWORD v103[3]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v104[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v105[2]; // [rsp+100h] [rbp+0h] BYREF
  int v106; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v107; // [rsp+118h] [rbp+18h]
  _QWORD v108[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v109[2]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v110; // [rsp+156h] [rbp+56h]
  int v111; // [rsp+164h] [rbp+64h]

  v8 = *((_WORD *)a4 + 4);
  v9 = this;
  v10 = a7;
  v11 = *(_QWORD *)((char *)a4 + 12);
  v12 = a2;
  v13 = *((_QWORD *)a2 + 1);
  v93 = a6 & 0x1000000;
  v94 = v13;
  v89 = v11;
  v91 = 0;
  v15 = *((unsigned int *)a4 + 5);
  v16 = a4;
  v90 = *((_DWORD *)a4 + 5);
  v87 = v8;
  v88 = v8 & 0x180;
  if ( !a7 || (v8 & 0x180) != 0 )
  {
    v17 = (_QWORD *)(*((_QWORD *)this + 2) + 16LL);
    if ( (_QWORD *)*v17 == v17 )
    {
      v18 = 0;
    }
    else
    {
      v15 = *((_QWORD *)this + 3);
      v18 = *v17 - 32LL;
      do
      {
        if ( *(_QWORD *)(v18 + 16) == v15 )
          break;
        v19 = *(_QWORD **)(v18 + 32);
        v18 = 0;
        if ( v19 != v17 )
          v18 = (__int64)(v19 - 4);
      }
      while ( v18 );
    }
    if ( (*(_BYTE *)(v18 + 48) & 2) != 0 )
    {
      v56 = *(_QWORD **)(v18 + 32);
      v18 = 0;
      if ( v56 != v17 )
        v18 = (__int64)(v56 - 4);
    }
    v20 = *(_QWORD *)v18;
    v21 = (char *)a3 + 80;
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v18 + 24LL) + 44LL) & 2) == 0
      || (v22 = 2, *(_BYTE *)(*((_QWORD *)v21 + 1) + 12LL)) )
    {
      v22 = 1;
    }
    v23 = (unsigned int *)*((_QWORD *)v21 + 2);
    if ( (v23[2] & 0x40) != 0 )
      v24 = (*((unsigned __int16 *)v23 + 5) + 7) & 0xFFFFFFF8;
    else
      v24 = *v23;
    if ( (*(_DWORD *)v12 & 0x1000LL) != 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      LOBYTE(v15) = 1;
      CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)v12 + 1), 0x20000000, v15);
      return (unsigned int)-1073741670;
    }
    v25 = v22 * v24 + 40;
    v26 = ((v22 * v24 + 47) & 0xFFFFFFF8) + 88;
    v27 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v26 > *v27 )
    {
      v27 = 0;
      v28 = v26 + 16;
      goto LABEL_16;
    }
    if ( !*((_BYTE *)v27 + 8) )
    {
      if ( (int)*((_QWORD *)v27 + 11) > (int)HIDWORD(*((_QWORD *)v27 + 11)) )
      {
        v31 = _InterlockedDecrement((volatile signed __int32 *)v27 + 22);
        if ( v31 >= (int)v27[23] && v31 >= 0 )
        {
          v58 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v27 + 4);
          goto LABEL_25;
        }
        _InterlockedIncrement((volatile signed __int32 *)v27 + 22);
      }
LABEL_23:
      v28 = v27[1];
LABEL_16:
      Pool2 = ExAllocatePool2(66, v28, 1766871885);
      v30 = (_DWORD *)Pool2;
      if ( (Pool2 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !Pool2 )
      {
LABEL_27:
        if ( v30 )
        {
          v30[4] = 7;
          *((_QWORD *)v30 + 5) = v20;
          v30[3] = v25;
          v30[2] = v25;
          *((_WORD *)v30 + 10) = 0;
          *((_OWORD *)v30 + 3) = 0;
          *((_OWORD *)v30 + 4) = 0;
          *((_QWORD *)v30 + 10) = 0;
          v30[8] = 0;
          if ( v25 )
          {
            *((_QWORD *)v30 + 3) = v30 + 22;
            memset(v30 + 22, 0, v25);
            v32 = (_QWORD *)*((_QWORD *)v30 + 3);
          }
          else
          {
            *((_QWORD *)v30 + 3) = 0;
            v32 = 0;
          }
          *v32 = 0;
          v32[1] = 0;
          *((_BYTE *)v32 + 16) = 0;
          if ( (v23[2] & 0x40) != 0 )
            v33 = (*((unsigned __int16 *)v23 + 5) + 7) & 0xFFFFFFF8;
          else
            v33 = *v23;
          memmove((char *)v32 + 20, v23, v33);
          v30[2] = v25;
          v30[8] = 0;
          *((_QWORD *)v30 + 5) = v20;
          if ( v21 )
          {
            v45 = *(_QWORD *)v21;
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v21 + 380LL));
            if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v45 + 560) )
              ++*(_DWORD *)(v45 + 384);
            else
              SmsPageLatch::AcquireShared((SmsPageLatch *)(v45 + 560), a2, 1);
            if ( *(char *)(*(_QWORD *)(v45 + 96) + 14LL) >= 0 )
              ++*((_DWORD *)a2 + 49);
            ++*(_DWORD *)(v45 + 388);
            v46 = *((_QWORD *)v21 + 1);
            v47 = *((_QWORD *)v21 + 2);
            v34 = *((unsigned int *)v21 + 6);
            v48 = *((_QWORD *)v21 + 4);
            v49 = *((_DWORD *)v21 + 7);
            if ( *((_QWORD *)v30 + 6) && (_BYTE)KdDebuggerEnabled )
              __debugbreak();
            *((_QWORD *)v30 + 6) = *(_QWORD *)v21;
            *((_QWORD *)v30 + 7) = v46;
            *((_QWORD *)v30 + 8) = v47;
            v30[18] = v34;
            *((_QWORD *)v30 + 10) = v48;
            v30[19] = v49;
            v50 = *(_QWORD *)v21;
            if ( *(_QWORD *)v21 && (!*(_BYTE *)(v50 + 392) && *(_QWORD *)(v50 + 96) == v20 || !*(_BYTE *)(v20 + 212)) )
              *((_BYTE *)v30 + 20) |= 1u;
          }
          else
          {
            *((_OWORD *)v30 + 3) = 0;
            *((_OWORD *)v30 + 4) = 0;
            *((_QWORD *)v30 + 10) = 0;
          }
          v35 = v30[2];
          if ( v35 )
          {
            v36 = (_QWORD *)*((_QWORD *)v30 + 3);
            if ( v32 )
            {
              if ( v32 != v36 )
                memmove(v36, v32, v35);
            }
            else
            {
              memset(v36, 0, (unsigned int)v30[2]);
            }
          }
          v12 = a2;
          v9 = this;
          v10 = a7;
          v8 = v87;
          *(_QWORD *)v30 = *((_QWORD *)a2 + 18);
          *((_QWORD *)a2 + 18) = v30;
          goto LABEL_39;
        }
        return (unsigned int)-1073741670;
      }
LABEL_26:
      *(_QWORD *)v30 = v27;
      v30 += 4;
      goto LABEL_27;
    }
    v57 = (struct _NPAGED_LOOKASIDE_LIST *)(v27 + 16);
    if ( *((_BYTE *)v27 + 9) )
      v58 = ExAllocateFromNPagedLookasideList(v57);
    else
      v58 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v57);
LABEL_25:
    v30 = v58;
    if ( v58 )
      goto LABEL_26;
    goto LABEL_23;
  }
  v60 = *((_QWORD *)this + 2);
  v61 = *((_QWORD *)a4 + 2);
  v62 = *((unsigned __int8 *)a7 + 2);
  *(_QWORD *)&v92[12] = 0;
  memset(v109, 0, sizeof(v109));
  *(_QWORD *)v92 = 0;
  *(_DWORD *)&v92[8] = 1572928;
  v63 = *(_OWORD *)a4;
  *(_DWORD *)&v92[20] = 0;
  v64 = *(_DWORD *)(v13 + 64);
  *(_OWORD *)v92 = v63;
  *(_QWORD *)&v92[16] = v61;
  InitChecksumBlobStream(
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + 248) + 24LL) + 72LL) + 8 * v62 + 3624),
    v13,
    (unsigned int)((_DWORD)v15 << v64),
    v92);
  inserted = TmsTableSet<CmsStreamSetCallbacks>::DeleteRow(*((_QWORD *)v9 + 2), v12, v65, a3);
  if ( inserted < 0 )
    return (unsigned int)inserted;
  ChecksumSizeInBytes = SmsRunHeader::GetChecksumSizeInBytes((SmsRunHeader *)v92, *((const struct CmsVolume **)v12 + 1));
  v67 = *((_QWORD *)v9 + 3);
  v68 = *((_QWORD *)v9 + 2);
  v97 = v92[8] & 3;
  v98 = v110;
  v99 = &v92[12];
  v100 = *(unsigned __int16 *)&v92[10];
  v101 = v111;
  v102 = v92;
  v96 = 12;
  inserted = TmsTableSet<CmsStreamSetCallbacks>::InsertRow(
               v68,
               v12,
               v67,
               (struct _CmsRow *)&v96,
               50,
               ChecksumSizeInBytes,
               0,
               (struct _SmsQuickIndex *)v109,
               0);
  if ( inserted < 0 )
    return (unsigned int)inserted;
  v16 = *(struct SmsRun **)&v109[0];
LABEL_39:
  if ( a5 )
  {
    v95[0] = *(_QWORD *)v16;
    v95[1] = *((unsigned int *)v16 + 5);
    v103[0] = v89;
    v103[1] = v90;
    if ( (v8 & 0x400) != 0 )
    {
      *((_WORD *)v16 + 4) &= ~0x400u;
    }
    else
    {
      v69 = *((_QWORD *)v9 + 2);
      if ( v88 )
      {
        v70 = SmsRunHeader::GetChecksumSizeInBytes(v16, *((const struct CmsVolume **)v12 + 1));
      }
      else
      {
        v71 = 0;
        v70 = 0;
      }
      inserted = CmsBPlusTable::AddToDeleteQueue(
                   *(CmsBPlusTable **)(v69 + 248),
                   v12,
                   (const struct _RANGE *)v95,
                   v34,
                   &v91,
                   (*((_WORD *)v16 + 4) & 0x20) != 0,
                   (*((_WORD *)v16 + 4) & 0x200) != 0,
                   v9,
                   v71,
                   v86,
                   v70);
      if ( inserted < 0 )
        return (unsigned int)inserted;
    }
    inserted = CmsStream::LogRedoForFree(v9, v12, (const struct _RANGE *)v103, (const struct _RANGE *)v95, v80);
    if ( inserted < 0 )
      return (unsigned int)inserted;
    inserted = CmsStream::LogRedoForAllocation(v9, v12, &v89, a5, 0);
    if ( inserted < 0 )
      return (unsigned int)inserted;
    v37 = v94;
    v91 += (unsigned __int64)*((unsigned int *)a5 + 2) << *(_DWORD *)(v94 + 64);
    *(_QWORD *)v16 = *(_QWORD *)a5;
  }
  else
  {
    v37 = v94;
  }
  if ( v10 )
  {
    v72 = *((unsigned __int8 *)v10 + 2);
    LOBYTE(v34) = 1;
    LOBYTE(v85) = 1;
    LOBYTE(v83) = 0;
    *(_QWORD *)v82 = (char *)v10 + *((unsigned __int8 *)v10 + 3);
    v73 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v9 + 2) + 248LL) + 24LL) + 72LL) + 8 * v72 + 3624);
    v74 = *(_DWORD *)(v37 + 64) - *(unsigned __int16 *)(v73 + 20);
    v104[0] = *(_QWORD *)v16;
    v104[1] = *((unsigned int *)v16 + 5);
    LOWORD(v80) = v72;
    inserted = CmsVolumeContainer::SetContainerRangeValid(
                 *(_QWORD *)(v37 + 3336),
                 v12,
                 v104,
                 v34,
                 v80,
                 a8 << v74,
                 *(_QWORD *)v82,
                 v83);
    if ( inserted < 0 )
      return (unsigned int)inserted;
    v51 = (char *)v10 + *((unsigned __int8 *)v10 + 3);
    if ( *(_WORD *)(v73 + 8) )
    {
      ChecksumLength = CmsChecksum::GetChecksumLength(
                         (CmsChecksum *)v73,
                         (unsigned __int64)v90 << *(_DWORD *)(*((_QWORD *)v12 + 1) + 64LL));
      v54 = (unsigned __int64)a8 << v74 << *(_DWORD *)(v73 + 12);
      if ( ChecksumLength == -1 )
        ChecksumLength = *((unsigned int *)v10 + 1) - v54;
      v51 = (char *)(v54 + v53);
    }
    else
    {
      ChecksumLength = 0;
    }
    memmove((char *)v16 + 24, v51, ChecksumLength);
    ChecksumType = SmsRunHeader::GetChecksumType(v16, *((const struct CmsVolume **)v12 + 1));
    v77 = SmsRunHeader::GetChecksumSizeInBytes(v16, v76);
    v84 = ChecksumType;
    v42 = a6;
    inserted = CmsStream::LogRedoForExtentModify(
                 v9,
                 v12,
                 (const struct _SRANGE *)&v89,
                 v78,
                 a6,
                 (char *)v16 + 24,
                 v77,
                 v84,
                 (unsigned int)v85);
    if ( inserted < 0 )
      return (unsigned int)inserted;
  }
  else
  {
    v105[0] = v89;
    v105[1] = v90;
    if ( byte_140262191 )
      goto LABEL_51;
    v38 = (_QWORD *)(*((_QWORD *)v9 + 2) + 16LL);
    v107 = v105;
    v106 = 16;
    if ( (_QWORD *)*v38 == v38 )
    {
      v39 = 0;
    }
    else
    {
      v39 = *v38 - 32LL;
      do
      {
        if ( *(_QWORD *)(v39 + 16) == *((_QWORD *)v9 + 3) )
          break;
        v40 = *(_QWORD **)(v39 + 32);
        v39 = 0;
        if ( v40 != v38 )
          v39 = (__int64)(v40 - 4);
      }
      while ( v39 );
    }
    if ( (*(_BYTE *)(v39 + 48) & 2) != 0 )
    {
      v59 = *(_QWORD **)(v39 + 32);
      v39 = 0;
      if ( v59 != v38 )
        v39 = (__int64)(v59 - 4);
    }
    if ( MsDisableRedoLogging
      || (*(_QWORD *)v12 & 0x2000000000LL) != 0
      || (*(_QWORD *)v12 & 0x20) != 0
      || (v55 = *((_QWORD *)v12 + 1)) != 0 && (*(_DWORD *)(v55 + 3460) & 0x400001) != 0 )
    {
LABEL_51:
      inserted = 0;
    }
    else
    {
      v79 = *(CmsBPlusTable **)v39;
      CmsTxMemLog::AddRedoRecord(*((_QWORD *)v12 + 52), *(_QWORD **)v39, 8u, 0, &v106, 0, 0, 0, (__int64)v85, 0, 0);
      if ( CmsBPlusTable::HasGlobalBindingSemantics(v79) )
      {
        *((_QWORD *)v12 + 14) = v79;
        *(_QWORD *)v12 |= 0x80000000000uLL;
      }
      if ( inserted < 0 )
        return (unsigned int)inserted;
    }
    v42 = a6;
    *((_WORD *)v16 + 4) &= 0xFE7Fu;
  }
  if ( v93 )
  {
    v108[0] = v89;
    v108[1] = v90;
    inserted = CmsStream::LogRedoForSetRangeEncrypted(v9, v12, (const struct _RANGE *)v108, (a6 & 0x1000000) != 0);
    if ( inserted < 0 )
      return (unsigned int)inserted;
    *((_WORD *)v16 + 4) |= 0x800u;
  }
  else
  {
    *((_WORD *)v16 + 4) &= ~0x800u;
  }
  v43 = *((_WORD *)v16 + 4) & 0xFDDF;
  *((_WORD *)v16 + 4) = v43;
  if ( (v42 & 0x40) != 0 )
    *((_WORD *)v16 + 4) = v43 | 0x10;
  if ( v91 )
  {
    LOWORD(v86) = 0;
    LOWORD(v85) = 0;
    LOBYTE(v81) = 0;
    LOBYTE(v80) = 1;
    return (unsigned int)CmsStream::UpdateStreamSummary(v9, v12, v91, 0, v80, v81, 0, 0, (_DWORD)v85, v86);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14006dc40  mov     [rsp-8+arg_10], rbx
0x14006dc45  mov     [rsp-8+arg_8], rdx
0x14006dc4a  mov     [rsp-8+arg_0], rcx
0x14006dc4f  push    rbp
0x14006dc50  push    rsi
0x14006dc51  push    rdi
0x14006dc52  push    r12
0x14006dc54  push    r13
0x14006dc56  push    r14
0x14006dc58  push    r15
0x14006dc5a  lea     rbp, [rsp-70h]
0x14006dc5f  sub     rsp, 170h
0x14006dc66  movzx   edi, word ptr [r9+8]
0x14006dc6b  mov     r14, rcx
0x14006dc6e  mov     eax, dword ptr [rbp+0A0h+arg_28]
0x14006dc74  mov     ecx, 180h
0x14006dc79  mov     r12, [rbp+0A0h+arg_30]
0x14006dc80  and     eax, 1000000h
0x14006dc85  movsd   xmm0, qword ptr [r9+0Ch]
0x14006dc8b  mov     r13, rdx
0x14006dc8e  mov     rdx, [rdx+8]
0x14006dc92  setnz   [rbp+0A0h+arg_18]
0x14006dc99  mov     [rbp+0A0h+var_108], eax
0x14006dc9c  xor     ebx, ebx
0x14006dc9e  movzx   eax, di
0x14006dca1  mov     [rbp+0A0h+var_100], rdx
0x14006dca5  and     ax, cx
0x14006dca8  movsd   [rsp+1A0h+var_138], xmm0
0x14006dcae  mov     [rsp+1A0h+var_128], rbx
0x14006dcb3  mov     r15, r8
0x14006dcb6  mov     r8d, [r9+14h]
0x14006dcba  mov     rsi, r9
0x14006dcbd  mov     [rsp+1A0h+var_130], r8d
0x14006dcc2  mov     [rsp+1A0h+var_140], di
0x14006dcc7  mov     [rsp+1A0h+var_13E], ax
0x14006dccc  test    r12, r12
0x14006dccf  jnz     loc_1401F6628
0x14006dcd5  mov     r9, [r14+10h]
0x14006dcd9  add     r9, 10h
0x14006dcdd  mov     rdx, [r9]
0x14006dce0  cmp     rdx, r9
0x14006dce3  jz      loc_14006DE15
0x14006dce9  mov     r8, [r14+18h]
0x14006dced  add     rdx, 0FFFFFFFFFFFFFFE0h
0x14006dcf1  cmp     [rdx+10h], r8
0x14006dcf5  jz      short loc_14006DD0E
0x14006dcf7  mov     rcx, [rdx+20h]
0x14006dcfb  mov     rdx, rbx
0x14006dcfe  cmp     rcx, r9
0x14006dd01  lea     rax, [rcx-20h]
0x14006dd05  cmovnz  rdx, rax
0x14006dd09  test    rdx, rdx
0x14006dd0c  jnz     short loc_14006DCF1
0x14006dd0e  test    byte ptr [rdx+30h], 2
0x14006dd12  jnz     loc_14006E20C
0x14006dd18  mov     r12, [rdx]
0x14006dd1b  add     r15, 50h ; 'P'
0x14006dd1f  mov     rax, [r12+18h]
0x14006dd24  mov     ecx, [rax+2Ch]
0x14006dd27  test    cl, 2
0x14006dd2a  jnz     loc_14006E223
0x14006dd30  mov     edx, 1
0x14006dd35  mov     r14, [r15+10h]
0x14006dd39  test    byte ptr [r14+8], 40h
0x14006dd3e  jnz     loc_14006DDC8
0x14006dd44  mov     ecx, [r14]
0x14006dd47  mov     eax, [r13+0]
0x14006dd4b  bt      rax, 0Ch
0x14006dd50  jb      loc_14006E1D0
0x14006dd56  imul    ecx, edx
0x14006dd59  lea     r13d, [rcx+28h]
0x14006dd5d  xor     ecx, ecx; ProcNumber
0x14006dd5f  lea     ebx, [r13+7]
0x14006dd63  and     ebx, 0FFFFFFF8h
0x14006dd66  add     ebx, 58h ; 'X'
0x14006dd69  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006dd70  nop     dword ptr [rax+rax+00h]
0x14006dd75  xor     edx, edx
0x14006dd77  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14006dd7d  lea     rdi, [rdx+rdx*2]
0x14006dd81  shl     rdi, 6
0x14006dd85  add     rdi, cs:qword_140262410
0x14006dd8c  mov     eax, [rdi]
0x14006dd8e  cmp     rbx, rax
0x14006dd91  jbe     short loc_14006DDD8
0x14006dd93  xor     edi, edi
0x14006dd95  lea     rdx, [rbx+10h]
0x14006dd99  mov     ecx, 42h ; 'B'
0x14006dd9e  mov     r8d, 6950534Dh
0x14006dda4  call    cs:__imp_ExAllocatePool2
0x14006ddab  nop     dword ptr [rax+rax+00h]
0x14006ddb0  mov     rbx, rax
0x14006ddb3  test    al, 0Fh
0x14006ddb5  jz      loc_1401F674B
0x14006ddbb  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14006ddc2  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14006ddc8  movzx   ecx, word ptr [r14+0Ah]
0x14006ddcd  add     ecx, 7
0x14006ddd0  and     ecx, 0FFFFFFF8h
0x14006ddd3  jmp     loc_14006DD47
0x14006ddd8  cmp     byte ptr [rdi+8], 0
0x14006dddc  jnz     loc_14006E23D
0x14006dde2  mov     rcx, [rdi+58h]
0x14006dde6  mov     rax, rcx
0x14006dde9  shr     rax, 20h
0x14006dded  cmp     ecx, eax
0x14006ddef  jle     short loc_14006DE10
0x14006ddf1  nop
0x14006ddf2  mov     ecx, 0FFFFFFFFh
0x14006ddf7  lock xadd [rdi+58h], ecx
0x14006ddfc  nop
0x14006ddfd  dec     ecx
0x14006ddff  mov     eax, [rdi+5Ch]
0x14006de02  cmp     ecx, eax
0x14006de04  jge     loc_14006E25C
0x14006de0a  nop
0x14006de0b  lock inc dword ptr [rdi+58h]
0x14006de0f  nop
0x14006de10  mov     edx, [rdi+4]
0x14006de13  jmp     short loc_14006DD99
0x14006de15  mov     rdx, rbx
0x14006de18  jmp     loc_14006DD0E
0x14006de1d  mov     rbx, rax
0x14006de20  test    rax, rax
0x14006de23  jz      short loc_14006DE10
0x14006de25  mov     [rbx], rdi
0x14006de28  add     rbx, 10h
0x14006de2c  test    rbx, rbx
0x14006de2f  jz      loc_14006E1EC
0x14006de35  mov     dword ptr [rbx+10h], 7
0x14006de3c  xor     eax, eax
0x14006de3e  mov     [rbx+28h], r12
0x14006de42  xorps   xmm0, xmm0
0x14006de45  mov     [rbx+0Ch], r13d
0x14006de49  mov     [rbx+8], r13d
0x14006de4d  mov     word ptr [rbx+14h], 0
0x14006de53  movups  xmmword ptr [rbx+30h], xmm0
0x14006de57  movups  xmmword ptr [rbx+40h], xmm0
0x14006de5b  mov     [rbx+50h], rax
0x14006de5f  mov     [rbx+20h], eax
0x14006de62  test    r13d, r13d
0x14006de65  jnz     loc_14006E046
0x14006de6b  mov     [rbx+18h], rax
0x14006de6f  mov     edi, eax
0x14006de71  mov     [rdi], rax
0x14006de74  mov     [rdi+8], rax
0x14006de78  mov     byte ptr [rdi+10h], 0
0x14006de7c  test    byte ptr [r14+8], 40h
0x14006de81  jnz     loc_14006E0A2
0x14006de87  mov     eax, [r14]
0x14006de8a  mov     r8d, eax; Size
0x14006de8d  lea     rcx, [rdi+14h]; void *
0x14006de91  mov     rdx, r14; Src
0x14006de94  call    memmove
0x14006de99  mov     [rbx+8], r13d
0x14006de9d  mov     dword ptr [rbx+20h], 0
0x14006dea4  mov     [rbx+28h], r12
0x14006dea8  test    r15, r15
0x14006deab  jnz     loc_14006E063
0x14006deb1  xorps   xmm0, xmm0
0x14006deb4  xor     eax, eax
0x14006deb6  movups  xmmword ptr [rbx+30h], xmm0
0x14006deba  movups  xmmword ptr [rbx+40h], xmm0
0x14006debe  mov     [rbx+50h], rax
0x14006dec2  mov     eax, [rbx+8]
0x14006dec5  test    eax, eax
0x14006dec7  jz      short loc_14006DEE6
0x14006dec9  mov     rcx, [rbx+18h]; void *
0x14006decd  test    rdi, rdi
0x14006ded0  jz      loc_14006E279
0x14006ded6  cmp     rdi, rcx
0x14006ded9  jz      short loc_14006DEE6
0x14006dedb  mov     r8d, eax; Size
0x14006dede  mov     rdx, rdi; Src
0x14006dee1  call    memmove
0x14006dee6  mov     r13, [rbp+0A0h+arg_8]
0x14006deed  mov     r14, [rbp+0A0h+arg_0]
0x14006def4  mov     r12, [rbp+0A0h+arg_30]
0x14006defb  movzx   edi, [rsp+1A0h+var_140]
0x14006df00  mov     rax, [r13+90h]
0x14006df07  mov     [rbx], rax
0x14006df0a  mov     [r13+90h], rbx
0x14006df11  mov     rbx, [rbp+0A0h+arg_20]
0x14006df18  test    rbx, rbx
0x14006df1b  jnz     loc_1401F6759
0x14006df21  mov     r10, [rbp+0A0h+var_100]
0x14006df25  test    r12, r12
0x14006df28  jnz     loc_1401F685F
0x14006df2e  cmp     cs:byte_140262191, r12b
0x14006df35  mov     rax, [rsp+1A0h+var_138]
0x14006df3a  mov     [rbp+0A0h+var_A0], rax
0x14006df3e  mov     eax, [rsp+1A0h+var_130]
0x14006df42  mov     [rbp+0A0h+var_98], rax
0x14006df46  jnz     short loc_14006DFA6
0x14006df48  mov     r9, [r14+10h]
0x14006df4c  lea     rax, [rbp+0A0h+var_A0]
0x14006df50  add     r9, 10h
0x14006df54  mov     [rbp+0A0h+var_88], rax
0x14006df58  mov     [rbp+0A0h+var_90], 10h
0x14006df5f  mov     rdx, [r9]
0x14006df62  cmp     rdx, r9
0x14006df65  jz      loc_14006E13F
0x14006df6b  mov     r8, [r14+18h]
0x14006df6f  add     rdx, 0FFFFFFFFFFFFFFE0h
0x14006df73  cmp     [rdx+10h], r8
0x14006df77  jz      short loc_14006DF8F
0x14006df79  mov     rcx, [rdx+20h]
0x14006df7d  xor     edx, edx
0x14006df7f  cmp     rcx, r9
0x14006df82  lea     rax, [rcx-20h]
0x14006df86  cmovnz  rdx, rax
0x14006df8a  test    rdx, rdx
0x14006df8d  jnz     short loc_14006DF73
0x14006df8f  test    byte ptr [rdx+30h], 2
0x14006df93  jnz     loc_14006E288
0x14006df99  cmp     cs:?MsDisableRedoLogging@@3EA, 0; uchar MsDisableRedoLogging
0x14006dfa0  jz      loc_14006E197
0x14006dfa6  xor     edx, edx
0x14006dfa8  mov     ebx, dword ptr [rbp+0A0h+arg_28]
0x14006dfae  mov     eax, 0FFFFFE7Fh
0x14006dfb3  and     [rsi+8], ax
0x14006dfb7  cmp     [rbp+0A0h+var_108], 0
0x14006dfbb  jnz     loc_14006E29E
0x14006dfc1  mov     eax, 0FFFFF7FFh
0x14006dfc6  and     [rsi+8], ax
0x14006dfca  movzx   eax, word ptr [rsi+8]
0x14006dfce  mov     ecx, 0FFFFFDDFh
0x14006dfd3  and     ax, cx
0x14006dfd6  mov     [rsi+8], ax
0x14006dfda  test    bl, 40h
0x14006dfdd  jz      short loc_14006DFE7
0x14006dfdf  or      ax, 10h
0x14006dfe3  mov     [rsi+8], ax
0x14006dfe7  mov     r8, [rsp+1A0h+var_128]
0x14006dfec  test    r8, r8
0x14006dfef  jz      short loc_14006E028
0x14006dff1  xor     eax, eax
0x14006dff3  xor     ecx, ecx
0x14006dff5  mov     [rsp+1A0h+var_158], ax
0x14006dffa  xor     r9d, r9d
0x14006dffd  mov     word ptr [rsp+1A0h+var_160], cx
0x14006e002  mov     rdx, r13
0x14006e005  mov     [rsp+1A0h+var_168], rax
0x14006e00a  mov     rcx, r14
0x14006e00d  mov     qword ptr [rsp+1A0h+var_170], rax
0x14006e012  mov     byte ptr [rsp+1A0h+var_178], al
0x14006e016  mov     byte ptr [rsp+1A0h+var_180], 1
0x14006e01b  call    ?UpdateStreamSummary@CmsStream@@QEAAJPEAVCmsTransactionContext@@_J1W4LogUndoUpdateStreamSummary@@W4LogRedoUpdateStreamSummary@@PEA_J4W4EMS_STREAM_SUMMARY_FLAGS@@5@Z; CmsStream::UpdateStreamSummary(CmsTransactionContext *,__int64,__int64,LogUndoUpdateStreamSummary,LogRedoUpdateStreamSummary,__int64 *,__int64 *,EMS_STREAM_SUMMARY_FLAGS,EMS_STREAM_SUMMARY_FLAGS)
0x14006e020  mov     edx, eax
0x14006e022  jmp     short loc_14006E028
0x14006e024  test    edx, edx
0x14006e026  jns     short loc_14006DFA8
0x14006e028  mov     rbx, [rsp+1A0h+arg_10]
0x14006e030  mov     eax, edx
0x14006e032  add     rsp, 170h
0x14006e039  pop     r15
0x14006e03b  pop     r14
0x14006e03d  pop     r13
0x14006e03f  pop     r12
0x14006e041  pop     rdi
0x14006e042  pop     rsi
0x14006e043  pop     rbp
0x14006e044  retn
0x14006e046  lea     rcx, [rbx+58h]; void *
0x14006e04a  mov     r8d, r13d; Size
0x14006e04d  xor     edx, edx; Val
0x14006e04f  mov     [rbx+18h], rcx
0x14006e053  call    memset
0x14006e058  mov     rdi, [rbx+18h]
0x14006e05c  xor     eax, eax
0x14006e05e  jmp     loc_14006DE71
0x14006e063  mov     r14, [r15]
0x14006e066  nop
0x14006e067  lock inc dword ptr [r14+17Ch]
0x14006e06f  lea     rcx, [r14+230h]
0x14006e076  nop
0x14006e077  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14006e07e  nop     dword ptr [rax+rax+00h]
0x14006e083  mov     r13, [rbp+0A0h+arg_8]
0x14006e08a  test    al, al
0x14006e08c  jnz     short loc_14006E0B2
0x14006e08e  mov     r8b, 1; bool
0x14006e091  lea     rcx, [r14+230h]; this
0x14006e098  mov     rdx, r13; struct CmsTransactionContext *
0x14006e09b  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x14006e0a0  jmp     short loc_14006E0B9
0x14006e0a2  movzx   eax, word ptr [r14+0Ah]
0x14006e0a7  add     eax, 7
0x14006e0aa  and     eax, 0FFFFFFF8h
0x14006e0ad  jmp     loc_14006DE8A
0x14006e0b2  inc     dword ptr [r14+180h]
0x14006e0b9  mov     rax, [r14+60h]
0x14006e0bd  cmp     byte ptr [rax+0Eh], 0
0x14006e0c1  jl      short loc_14006E0CA
0x14006e0c3  inc     dword ptr [r13+0C4h]
0x14006e0ca  inc     dword ptr [r14+184h]
0x14006e0d1  cmp     qword ptr [rbx+30h], 0
0x14006e0d6  mov     rcx, [r15]
0x14006e0d9  mov     rdx, [r15+8]
0x14006e0dd  mov     r8, [r15+10h]
  ... truncated ...
```
