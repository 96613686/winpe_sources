# TxfDeleteFile

- ea: `0x14018f790`
- end: `0x140190326`
- name: `TxfDeleteFile`
- size: `2966`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `27`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update`

## callers

- `0x1401c3750`
- `0x140227568`
- `0x14024c8e4`

## callees

- `0x14000cb00`
- `0x14000d1e0`
- `0x14000ea70`
- `0x140012e10`
- `0x140012e70`
- `0x14001e810`
- `0x1400211b0`
- `0x1400331f8`
- `0x1400592c0`
- `0x140059740`
- `0x14012a000`
- `0x14012bac0`
- `0x1401403d0`
- `0x140140fac`
- `0x140154d60`
- `0x14018c660`
- `0x14018e054`
- `0x14018e624`
- `0x14018e688`
- `0x14018f790`
- `0x14019032c`
- `0x140190a20`
- `0x140191424`
- `0x140195188`
- `0x1401959b4`
- `0x1401e3280`
- `0x14020f080`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14018f8cc`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14018f8cc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ab66f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ab66f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14018ffec`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14018ffec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140190074`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140190074`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190269`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401902f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ab68a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ab72a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140190269`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401902f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ab68a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ab72a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14018f9d2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14018f9d2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14019004b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14019004b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140190093`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140190093`
- `ntoskrnl!ExReleaseResourceLite` at `0x140190114`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401901f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ab6bb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140190114`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401901f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ab6bb`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14018fdc3`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14018fdc3`

## pseudocode

```c
void __fastcall TxfDeleteFile(CLFS_LSN *a1, __int64 a2, __int64 a3, int a4, char *a5, _QWORD *a6, __int64 a7)
{
  _QWORD *v10; // r14
  __int64 v11; // r12
  __int64 v12; // rcx
  __int64 v13; // r8
  char *v14; // r15
  char v15; // al
  __int16 v16; // ax
  __int64 v17; // rcx
  __int64 v18; // rcx
  _WORD *PoolWithTag; // r15
  __int16 v20; // cx
  __int64 v21; // rax
  __int16 v22; // cx
  __int16 v23; // r12
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  char v27; // r12
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 MatchingLcbPair; // rsi
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r15
  struct _ERESOURCE *v34; // rcx
  _OWORD *v35; // r12
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  _QWORD *v39; // rcx
  __int64 v40; // rax
  int v41; // ecx
  __int64 v42; // rsi
  __int64 i; // rsi
  _QWORD *v44; // rcx
  int v45; // [rsp+20h] [rbp-2E8h]
  int v46; // [rsp+20h] [rbp-2E8h]
  char v47; // [rsp+70h] [rbp-298h] BYREF
  char v48; // [rsp+71h] [rbp-297h]
  char v49; // [rsp+72h] [rbp-296h]
  _WORD v50[2]; // [rsp+74h] [rbp-294h] BYREF
  char v51; // [rsp+78h] [rbp-290h]
  char v52; // [rsp+79h] [rbp-28Fh] BYREF
  __int16 v53; // [rsp+7Ah] [rbp-28Eh]
  int v54; // [rsp+7Ch] [rbp-28Ch]
  __int64 v55; // [rsp+80h] [rbp-288h] BYREF
  __int64 ullOffset; // [rsp+88h] [rbp-280h]
  __int64 v57; // [rsp+90h] [rbp-278h]
  ULONG IsResourceAcquiredSharedLite; // [rsp+98h] [rbp-270h]
  _OWORD *v59; // [rsp+A0h] [rbp-268h]
  __int64 v60; // [rsp+A8h] [rbp-260h]
  CLFS_LSN *v61; // [rsp+B0h] [rbp-258h]
  __int64 v62; // [rsp+B8h] [rbp-250h] BYREF
  _WORD *v63; // [rsp+C0h] [rbp-248h]
  _QWORD *v64; // [rsp+C8h] [rbp-240h]
  __int64 v65; // [rsp+D0h] [rbp-238h]
  __int64 v66; // [rsp+D8h] [rbp-230h]
  __int64 v67; // [rsp+E0h] [rbp-228h]
  __int64 v68; // [rsp+E8h] [rbp-220h]
  char *v69; // [rsp+F0h] [rbp-218h]
  __int64 v70; // [rsp+F8h] [rbp-210h]
  __int64 v71; // [rsp+100h] [rbp-208h]
  __int64 v72; // [rsp+110h] [rbp-1F8h]
  _QWORD v73[14]; // [rsp+120h] [rbp-1E8h] BYREF
  _QWORD v74[14]; // [rsp+190h] [rbp-178h] BYREF
  _QWORD v75[14]; // [rsp+200h] [rbp-108h] BYREF
  CLFS_WRITE_ENTRY v76[5]; // [rsp+270h] [rbp-98h] BYREF

  v54 = a4;
  v61 = a1;
  v65 = a2;
  v10 = a6;
  v70 = (__int64)a6;
  v72 = (__int64)a6;
  v55 = a7;
  v57 = *(_QWORD *)(a3 + 24);
  v71 = v57;
  ullOffset = a1[50].ullOffset;
  v68 = *(_QWORD *)(a2 + 96);
  v11 = v68;
  v60 = 0;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  v59 = 0;
  memset(v74, 0, sizeof(v74));
  v51 = *(_BYTE *)(*(_QWORD *)(a3 + 192) + 65LL);
  v63 = 0;
  v53 = *(_WORD *)(a2 + 190);
  memset(v73, 0, sizeof(v73));
  memset(v75, 0, 0x64u);
  v52 = 0;
  IsResourceAcquiredSharedLite = ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v68 + 48) + 184LL)
                                                                                       + 104LL)
                                                                           + 64LL));
  if ( !a6 )
  {
    v74[1] = &v74[4];
    v74[3] = &v74[7];
    LODWORD(v74[0]) = 1572864;
    LODWORD(v74[2]) = 3407872;
    v10 = v74;
  }
  v64 = v10;
  v14 = &v47;
  if ( a5 )
    v14 = a5;
  v69 = v14;
  v15 = v54;
  if ( (v54 & 2) == 0 )
  {
    NtfsAcquireExclusiveFcb(a1, a2, 0, 0);
    v49 = 1;
    v15 = v54;
  }
  if ( (v15 & 4) == 0 )
  {
    NtfsAcquireExclusiveScbEx(a1, v57, 0);
    v48 = 1;
  }
  if ( !*v14 )
  {
    if ( v53 != 1 )
      goto LABEL_11;
    NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(*(_QWORD *)(a2 + 320) + 80LL), 0);
    *v14 = 1;
    v47 = 1;
  }
  if ( v53 == 1 && (*(_DWORD *)(a2 + 176) & 0x400) != 0 )
  {
    LOBYTE(v13) = 1;
    NtfsAcquireResourceExclusive(v12, *(_QWORD *)(v11 + 152), v13);
    v60 = *(_QWORD *)(v11 + 152);
    v33 = v60;
    TxfInsertReparseIsoEntry((_DWORD)a1, v11, 2, ullOffset, *(_DWORD *)(a2 + 180), *(_QWORD *)(a2 + 8), 1);
    TxfClearTxnVisibleReparseIsoEntry(v11, *(unsigned int *)(a2 + 180), *(_QWORD *)(a2 + 8), 0);
    if ( *(_WORD *)v33 == 1794 )
      v34 = (struct _ERESOURCE *)(*(_QWORD *)(v33 + 104) + 64LL);
    else
      v34 = *(struct _ERESOURCE **)(v33 + 8);
    ExReleaseResourceLite(v34);
    v60 = 0;
  }
LABEL_11:
  TxfRemoveLink((int)a1, a2, v55);
  v16 = *((_WORD *)v10 + 8);
  v17 = (__int64)(v10 + 2);
  if ( v16 )
    v17 = (__int64)v10;
  v67 = v17;
  v18 = (__int64)v10;
  if ( v16 )
    v18 = (__int64)(v10 + 2);
  v66 = v18;
  LODWORD(v55) = 200;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0xC8u, 0x68667854u);
  v63 = PoolWithTag;
  v76[0].Buffer = PoolWithTag;
  v76[0].ByteLength = 200;
  v50[0] = 1;
  memset(PoolWithTag, 0, 0xC8u);
  v20 = 0;
  if ( (*(_DWORD *)(ullOffset + 16) & 0x2000000) != 0 )
  {
    *PoolWithTag = 2;
    v20 = 2;
  }
  *PoolWithTag = v20 | 1;
  *((_DWORD *)PoolWithTag + 1) = 3;
  *((_QWORD *)PoolWithTag + 2) = *(_QWORD *)(a2 + 8);
  *((_QWORD *)PoolWithTag + 1) = *(_QWORD *)(a2 + 312);
  TxfAddFileIdentityToLogRec(
    (_DWORD)a1,
    (unsigned int)v76,
    (unsigned int)v50,
    (unsigned int)&v55,
    (__int64)(PoolWithTag + 48),
    v57);
  *((_QWORD *)PoolWithTag + 10) = *(_QWORD *)(a2 + 312);
  v21 = *(_QWORD *)(a2 + 328);
  if ( *(_QWORD *)(v21 + 152) )
    TxfAddUnicodeStringToLogRec(
      (unsigned int)v76,
      (unsigned int)v50,
      (unsigned int)&v55,
      (_DWORD)PoolWithTag + 88,
      *(_QWORD *)(v21 + 152));
  TxfAddUnicodeStringToLogRec((unsigned int)v76, (unsigned int)v50, (unsigned int)&v55, (_DWORD)PoolWithTag + 112, v66);
  if ( v67 )
    TxfAddUnicodeStringToLogRec(
      (unsigned int)v76,
      (unsigned int)v50,
      (unsigned int)&v55,
      (_DWORD)PoolWithTag + 116,
      v67);
  *((_BYTE *)PoolWithTag + 176) = v51;
  *(_OWORD *)(PoolWithTag + 60) = *(_OWORD *)(a2 + 128);
  *(_OWORD *)(PoolWithTag + 68) = *(_OWORD *)(a2 + 144);
  *(_OWORD *)(PoolWithTag + 76) = *(_OWORD *)(a2 + 160);
  *((_QWORD *)PoolWithTag + 21) = *(_QWORD *)(a2 + 176);
  PoolWithTag[98] |= (*(_DWORD *)(a2 + 176) & 0x10000000) != 0;
  v22 = PoolWithTag[98] | (4 * (v54 & 1));
  PoolWithTag[98] = v22;
  v23 = v53;
  if ( v53 == 1 )
  {
    v22 |= 0x40u;
    PoolWithTag[98] = v22;
  }
  v24 = *(_QWORD *)(a2 + 328);
  if ( v24 && (*(_DWORD *)(v24 + 4) & 0x100) != 0 )
    PoolWithTag[98] = v22 | 2;
  v62 = TxfTransWriteLogArray(ullOffset, v76, v50[0], 0, a1, 1, 1, (*(_BYTE *)PoolWithTag & 2) != 0 ? v55 : 0, 0).ullOffset;
  TxfUpdateTxfDataAttributeMembers(
    (int)a1,
    *(_QWORD *)(v57 + 184),
    v45,
    0,
    ~(unsigned __int8)(*(_DWORD *)(*(_QWORD *)(v57 + 184) + 4LL) >> 20) & 2,
    0,
    0,
    (__int64)&v62,
    0,
    0,
    0);
  TxfUpdateTxfDataAttributeMembers(
    (int)a1,
    a2,
    v46,
    0,
    ((*(_DWORD *)(a2 + 4) >> 20) & 1) == 0,
    (__int64)&v62,
    0,
    0,
    0,
    0,
    0);
  if ( v23 == 1 )
  {
    LOWORD(v75[8]) = (unsigned __int8)TxfConvertTxfFileIdToMungedName(a2 + 312, (char *)&v75[8] + 2);
    v75[0] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 320) + 80LL) + 184LL) + 8LL);
    LODWORD(v73[0]) = 0;
    v73[1] = 0;
    LOWORD(v73[2]) = 2 * LOBYTE(v75[8]);
    WORD1(v73[2]) = v73[2];
    v73[3] = (char *)&v75[8] + 2;
    NtfsAddLink((_DWORD)a1, a2, (__int64)v75, 0, (__int64)&v52, 0, 0, (__int64)v73, 0);
    v26 = NtfsAddStructToRollbackList(a1, 1827, a2, 1);
    ++*(_WORD *)(v26 + 104);
    ++*(_WORD *)(v26 + 106);
    *(_DWORD *)(v26 + 4) |= 2u;
    ++*(_WORD *)(a2 + 188);
    ++*(_WORD *)(a2 + 190);
    v35 = ExAllocateFromLookasideListEx(&TxfDeletedLinkLookasideList);
    v59 = v35;
    *v35 = 0;
    v35[1] = 0;
    *((_QWORD *)v35 + 4) = 0;
    *((_QWORD *)v35 + 3) = *(_QWORD *)(a2 + 312);
    *((_QWORD *)v35 + 2) = *(_QWORD *)(a2 + 240);
    v36 = *(_QWORD *)(a2 + 328);
    *((_QWORD *)v35 + 4) = v36;
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v36 + 40) + 16LL) + 6176LL));
    ++*(_WORD *)(*((_QWORD *)v35 + 4) + 16LL);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v35 + 4) + 40LL) + 16LL) + 6176LL));
    ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(ullOffset + 24) + 80LL), 1u);
    v37 = ullOffset;
    v38 = ullOffset + 176;
    v39 = *(_QWORD **)(ullOffset + 184);
    if ( *v39 != ullOffset + 176 )
      __fastfail(3u);
    *(_QWORD *)v35 = v38;
    *((_QWORD *)v35 + 1) = v39;
    *v39 = v35;
    *(_QWORD *)(v38 + 8) = v35;
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v37 + 24) + 80LL));
    v40 = NtfsAddStructToRollbackList(a1, 1828, *(_QWORD *)(a2 + 328), 1);
    v41 = *(_DWORD *)(v40 + 4);
    v25 = 2;
    if ( (v41 & 2) == 0 )
    {
      *(_QWORD *)(v40 + 32) = v35;
      *(_DWORD *)(v40 + 4) = v41 | 2;
    }
    v59 = 0;
  }
  v27 = v54;
  if ( (v54 & 0x10) != 0 )
  {
    NtfsCheckpointCurrentTransaction(a1);
    v28 = v68;
    v29 = *(_QWORD *)(v68 + 40);
    if ( v29 && ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v29 + 184) + 104LL) + 64LL)) )
      NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v28 + 40) + 184LL), 0);
    if ( !IsResourceAcquiredSharedLite )
      NtfsReleaseExclusiveScbIfOwned(a1, *(_QWORD *)(v28 + 48));
    if ( v47 )
    {
      NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 320) + 80LL) + 184LL), 0);
      *v69 = 0;
      v47 = 0;
    }
    NtfsReleaseQuotaControlIfOwned(a1);
  }
  if ( (v27 & 8) == 0 )
  {
    if ( (*(_DWORD *)(a2 + 176) & 0x10000000) != 0 )
    {
      v42 = *(_QWORD *)(a2 + 64);
      if ( v42 != a2 + 64 )
      {
        for ( i = v42 - 168; i != a2 - 104; i = *(_QWORD *)(i + 168) - 168LL )
        {
          if ( *(_DWORD *)(i + 256) == 160 && *(_WORD *)(i + 656) )
            NtfsDeleteNormalizedName(a1, i);
        }
      }
    }
    MatchingLcbPair = NtfsFindMatchingLcbPair(a3, v25);
    NtfsRemovePrefix(v31, a3);
    if ( (*(_DWORD *)(a3 + 4) & 0x20) != 0 )
    {
      NtfsRemoveHashEntry(a1, *(_QWORD *)(*(_QWORD *)(a3 + 48) + 96LL) + 4968LL, *(unsigned int *)(a3 + 184), a3);
      *(_DWORD *)(a3 + 184) = 0;
      ClearFlagInterlocked(a3 + 4, 32);
    }
    SetFlagInterlocked(a3 + 4, 2);
    *(_DWORD *)(a3 + 180) = 0;
    *(_DWORD *)(a3 + 156) = 0;
    if ( MatchingLcbPair )
    {
      NtfsRemovePrefix(v32, MatchingLcbPair);
      if ( (*(_DWORD *)(MatchingLcbPair + 4) & 0x20) != 0 )
      {
        NtfsRemoveHashEntry(
          a1,
          *(_QWORD *)(*(_QWORD *)(MatchingLcbPair + 48) + 96LL) + 4968LL,
          *(unsigned int *)(MatchingLcbPair + 184),
          MatchingLcbPair);
        *(_DWORD *)(MatchingLcbPair + 184) = 0;
        ClearFlagInterlocked(MatchingLcbPair + 4, 32);
      }
      SetFlagInterlocked(MatchingLcbPair + 4, 2);
      *(_DWORD *)(MatchingLcbPair + 180) = 0;
      *(_DWORD *)(MatchingLcbPair + 156) = 0;
    }
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( v48 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(v57 + 184), 0);
  if ( v49 )
    NtfsReleaseFcbEx(a1, a2, 0);
  if ( !v70 )
  {
    v44 = (_QWORD *)v10[3];
    if ( v44 != v10 + 7 )
      ExFreePoolWithTag(v44, 0);
    v10[1] = v10 + 4;
    v10[3] = v10 + 7;
    *(_DWORD *)v10 = 1572864;
    *((_DWORD *)v10 + 4) = 3407872;
  }
  if ( v47 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 320) + 80LL) + 184LL), 0);
}

```

## disassembly

```asm
0x14018f790  push    rbx
0x14018f792  push    rsi
0x14018f793  push    rdi
0x14018f794  push    r12
0x14018f796  push    r13
0x14018f798  push    r14
0x14018f79a  push    r15
0x14018f79c  sub     rsp, 2D0h
0x14018f7a3  mov     rax, cs:__security_cookie
0x14018f7aa  xor     rax, rsp
0x14018f7ad  mov     [rsp+308h+var_48], rax
0x14018f7b5  mov     [rsp+308h+var_28C], r9d
0x14018f7ba  mov     r13, r8
0x14018f7bd  mov     rbx, rdx
0x14018f7c0  mov     rdi, rcx
0x14018f7c3  mov     [rsp+308h+var_258], rcx
0x14018f7cb  mov     [rsp+308h+var_238], rdx
0x14018f7d3  mov     rsi, [rsp+308h+arg_20]
0x14018f7db  mov     r14, [rsp+308h+arg_28]
0x14018f7e3  mov     [rsp+308h+var_210], r14
0x14018f7eb  mov     [rsp+308h+var_1F8], r14
0x14018f7f3  mov     rax, [rsp+308h+arg_30]
0x14018f7fb  mov     [rsp+308h+var_288], rax
0x14018f803  mov     rax, [r8+18h]
0x14018f807  mov     [rsp+308h+var_278], rax
0x14018f80f  mov     [rsp+308h+var_208], rax
0x14018f817  mov     rax, [rcx+190h]
0x14018f81e  mov     [rsp+308h+var_280], rax
0x14018f826  mov     r12, [rdx+60h]
0x14018f82a  mov     [rsp+308h+var_220], r12
0x14018f832  xor     ecx, ecx
0x14018f834  xor     eax, eax
0x14018f836  mov     [rsp+308h+var_260], rax
0x14018f83e  mov     [rsp+308h+var_296], cl
0x14018f842  mov     [rsp+308h+var_297], cl
0x14018f846  mov     [rsp+308h+var_298], cl
0x14018f84a  mov     [rsp+308h+var_268], rax
0x14018f852  lea     r15d, [rcx+70h]
0x14018f856  mov     r8d, r15d; Size
0x14018f859  xor     edx, edx; Val
0x14018f85b  lea     rcx, [rsp+308h+var_178]; void *
0x14018f863  call    memset
0x14018f868  mov     rax, [r13+0C0h]
0x14018f86f  mov     al, [rax+41h]
0x14018f872  mov     [rsp+308h+var_290], al
0x14018f876  mov     [rsp+308h+var_248], 0
0x14018f882  movzx   eax, word ptr [rbx+0BEh]
0x14018f889  mov     [rsp+308h+var_28E], ax
0x14018f88e  mov     r8d, r15d; Size
0x14018f891  xor     edx, edx; Val
0x14018f893  lea     rcx, [rsp+308h+var_1E8]; void *
0x14018f89b  call    memset
0x14018f8a0  xor     edx, edx; Val
0x14018f8a2  lea     r8d, [r15-0Ch]; Size
0x14018f8a6  lea     rcx, [rsp+308h+var_108]; void *
0x14018f8ae  call    memset
0x14018f8b3  mov     [rsp+308h+var_28F], 0
0x14018f8b8  mov     rax, [r12+30h]
0x14018f8bd  mov     rcx, [rax+0B8h]
0x14018f8c4  mov     rcx, [rcx+68h]
0x14018f8c8  add     rcx, 40h ; '@'; Resource
0x14018f8cc  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14018f8d3  nop     dword ptr [rax+rax+00h]
0x14018f8d8  mov     [rsp+308h+var_270], eax
0x14018f8df  test    r14, r14
0x14018f8e2  jnz     short loc_14018F922
0x14018f8e4  lea     rax, [rsp+308h+var_158]
0x14018f8ec  mov     [rsp+308h+var_170], rax
0x14018f8f4  lea     rax, [rsp+308h+var_140]
0x14018f8fc  mov     [rsp+308h+var_160], rax
0x14018f904  mov     [rsp+308h+var_178], 180000h
0x14018f90f  mov     [rsp+308h+var_168], 340000h
0x14018f91a  lea     r14, [rsp+308h+var_178]
0x14018f922  mov     [rsp+308h+var_240], r14
0x14018f92a  lea     r15, [rsp+308h+var_298]
0x14018f92f  test    rsi, rsi
0x14018f932  cmovnz  r15, rsi
0x14018f936  mov     [rsp+308h+var_218], r15
0x14018f93e  mov     eax, [rsp+308h+var_28C]
0x14018f942  test    al, 2
0x14018f944  jz      loc_1401901AE
0x14018f94a  mov     esi, 1
0x14018f94f  test    al, 4
0x14018f951  jz      loc_1401901D2
0x14018f957  cmp     byte ptr [r15], 0
0x14018f95b  jz      loc_14018FF99
0x14018f961  cmp     [rsp+308h+var_28E], si
0x14018f966  jz      loc_14018FF07
0x14018f96c  mov     rax, [rsp+308h+var_288]
0x14018f974  mov     [rsp+308h+var_2E8], rax; __int64
0x14018f979  mov     r9, r14
0x14018f97c  mov     r8, r13
0x14018f97f  mov     rdx, rbx; int
0x14018f982  mov     rcx, rdi; int
0x14018f985  call    TxfRemoveLink
0x14018f98a  lea     rdx, [r14+10h]
0x14018f98e  movzx   eax, word ptr [rdx]
0x14018f991  mov     rcx, rdx
0x14018f994  test    ax, ax
0x14018f997  cmovnz  rcx, r14
0x14018f99b  mov     [rsp+308h+var_228], rcx
0x14018f9a3  mov     rcx, r14
0x14018f9a6  cmovnz  rcx, rdx
0x14018f9aa  mov     [rsp+308h+var_230], rcx
0x14018f9b2  mov     r12d, 0C8h
0x14018f9b8  mov     dword ptr [rsp+308h+var_288], r12d
0x14018f9c0  mov     ecx, cs:PoolType
0x14018f9c6  or      ecx, 10h; PoolType
0x14018f9c9  mov     r8d, 68667854h; Tag
0x14018f9cf  mov     edx, r12d; NumberOfBytes
0x14018f9d2  call    cs:__imp_ExAllocatePoolWithTag
0x14018f9d9  nop     dword ptr [rax+rax+00h]
0x14018f9de  mov     r15, rax
0x14018f9e1  mov     [rsp+308h+var_248], rax
0x14018f9e9  mov     [rsp+308h+var_98], rax
0x14018f9f1  mov     [rsp+308h+var_90], r12d
0x14018f9f9  mov     [rsp+308h+var_294], si
0x14018f9fe  mov     r8d, r12d; Size
0x14018fa01  xor     edx, edx; Val
0x14018fa03  mov     rcx, rax; void *
0x14018fa06  call    memset
0x14018fa0b  xor     ecx, ecx
0x14018fa0d  mov     rax, [rsp+308h+var_280]
0x14018fa15  test    dword ptr [rax+10h], 2000000h
0x14018fa1c  jz      short loc_14018FA28
0x14018fa1e  lea     eax, [rcx+2]
0x14018fa21  mov     [r15], ax
0x14018fa25  movzx   ecx, ax
0x14018fa28  or      cx, si
0x14018fa2b  mov     [r15], cx
0x14018fa2f  mov     dword ptr [r15+4], 3
0x14018fa37  mov     rax, [rbx+8]
0x14018fa3b  mov     [r15+10h], rax
0x14018fa3f  lea     r12, [rbx+138h]
0x14018fa46  mov     rax, [r12]
0x14018fa4a  mov     [r15+8], rax
0x14018fa4e  lea     rax, [r15+60h]
0x14018fa52  mov     rcx, [rsp+308h+var_278]
0x14018fa5a  mov     qword ptr [rsp+308h+var_2E0], rcx
0x14018fa5f  mov     [rsp+308h+var_2E8], rax
0x14018fa64  lea     r9, [rsp+308h+var_288]
0x14018fa6c  lea     r8, [rsp+308h+var_294]
0x14018fa71  lea     rdx, [rsp+308h+var_98]
0x14018fa79  mov     rcx, rdi
0x14018fa7c  call    TxfAddFileIdentityToLogRec
0x14018fa81  mov     rax, [r12]
0x14018fa85  mov     [r15+50h], rax
0x14018fa89  mov     rax, [rbx+148h]
0x14018fa90  mov     rcx, [rax+98h]
0x14018fa97  test    rcx, rcx
0x14018fa9a  jnz     loc_14019020E
0x14018faa0  mov     rax, [rsp+308h+var_230]
0x14018faa8  mov     [rsp+308h+var_2E8], rax
0x14018faad  lea     r9, [r15+70h]
0x14018fab1  lea     r8, [rsp+308h+var_288]
0x14018fab9  lea     rdx, [rsp+308h+var_294]
0x14018fabe  lea     rcx, [rsp+308h+var_98]
0x14018fac6  call    TxfAddUnicodeStringToLogRec
0x14018facb  mov     rax, [rsp+308h+var_228]
0x14018fad3  xor     edx, edx
0x14018fad5  test    rax, rax
0x14018fad8  jz      short loc_14018FAFF
0x14018fada  lea     r9, [r15+74h]
0x14018fade  mov     [rsp+308h+var_2E8], rax
0x14018fae3  lea     r8, [rsp+308h+var_288]
0x14018faeb  lea     rdx, [rsp+308h+var_294]
0x14018faf0  lea     rcx, [rsp+308h+var_98]
0x14018faf8  call    TxfAddUnicodeStringToLogRec
0x14018fafd  xor     edx, edx
0x14018faff  mov     al, [rsp+308h+var_290]
0x14018fb03  mov     [r15+0B0h], al
0x14018fb0a  movups  xmm0, xmmword ptr [rbx+80h]
0x14018fb11  movups  xmmword ptr [r15+78h], xmm0
0x14018fb16  movups  xmm1, xmmword ptr [rbx+90h]
0x14018fb1d  movups  xmmword ptr [r15+88h], xmm1
0x14018fb25  movups  xmm0, xmmword ptr [rbx+0A0h]
0x14018fb2c  movups  xmmword ptr [r15+98h], xmm0
0x14018fb34  movsd   xmm1, qword ptr [rbx+0B0h]
0x14018fb3c  movsd   qword ptr [r15+0A8h], xmm1
0x14018fb45  mov     eax, [rbx+0B0h]
0x14018fb4b  shr     eax, 1Ch
0x14018fb4e  and     ax, si
0x14018fb51  or      [r15+0C4h], ax
0x14018fb59  movzx   ecx, word ptr [rsp+308h+var_28C]
0x14018fb5e  and     cx, si
0x14018fb61  shl     cx, 2
0x14018fb65  or      cx, [r15+0C4h]
0x14018fb6d  mov     [r15+0C4h], cx
0x14018fb75  movzx   r12d, [rsp+308h+var_28E]
0x14018fb7b  cmp     r12w, si
0x14018fb7f  jnz     short loc_14018FB8D
0x14018fb81  or      cx, 40h
0x14018fb85  mov     [r15+0C4h], cx
0x14018fb8d  mov     rax, [rbx+148h]
0x14018fb94  test    rax, rax
0x14018fb97  jnz     loc_14018FFC7
0x14018fb9d  mov     al, [r15]
0x14018fba0  and     al, 2
0x14018fba2  neg     al
0x14018fba4  sbb     ecx, ecx
0x14018fba6  and     ecx, dword ptr [rsp+308h+var_288]
0x14018fbad  movzx   r8d, [rsp+308h+var_294]
0x14018fbb3  mov     [rsp+308h+var_2C8], rdx
0x14018fbb8  mov     dword ptr [rsp+308h+var_2D0], ecx
0x14018fbbc  mov     [rsp+308h+var_2D8], esi
0x14018fbc0  mov     [rsp+308h+var_2E0], esi
0x14018fbc4  mov     [rsp+308h+var_2E8], rdi; int
0x14018fbc9  xor     r9d, r9d
0x14018fbcc  lea     rdx, [rsp+308h+var_98]
0x14018fbd4  mov     rcx, [rsp+308h+var_280]
0x14018fbdc  call    TxfTransWriteLogArray
0x14018fbe1  mov     [rsp+308h+var_250], rax
0x14018fbe9  mov     rax, [rsp+308h+var_278]
0x14018fbf1  mov     rdx, [rax+0B8h]; int
0x14018fbf8  mov     eax, [rdx+4]
0x14018fbfb  shr     eax, 14h
0x14018fbfe  not     eax
0x14018fc00  and     eax, 2
0x14018fc03  xor     r8d, r8d
0x14018fc06  mov     [rsp+308h+var_2A8], r8; __int64
0x14018fc0b  mov     [rsp+308h+var_2B0], r8; __int64
0x14018fc10  mov     [rsp+308h+var_2B8], r8; __int64
0x14018fc15  lea     rcx, [rsp+308h+var_250]
0x14018fc1d  mov     [rsp+308h+var_2C0], rcx; __int64
0x14018fc22  mov     [rsp+308h+var_2C8], r8; __int64
0x14018fc27  mov     [rsp+308h+var_2D0], r8; __int64
0x14018fc2c  mov     [rsp+308h+var_2D8], eax; int
0x14018fc30  mov     [rsp+308h+var_2E0], r8d; int
0x14018fc35  mov     rcx, rdi; int
0x14018fc38  call    TxfUpdateTxfDataAttributeMembers
0x14018fc3d  mov     eax, [rbx+4]
0x14018fc40  shr     eax, 14h
0x14018fc43  not     eax
0x14018fc45  and     eax, esi
0x14018fc47  xor     edx, edx
0x14018fc49  mov     [rsp+308h+var_2A8], rdx; __int64
0x14018fc4e  mov     [rsp+308h+var_2B0], rdx; __int64
0x14018fc53  mov     [rsp+308h+var_2B8], rdx; __int64
0x14018fc58  mov     [rsp+308h+var_2C0], rdx; __int64
0x14018fc5d  mov     [rsp+308h+var_2C8], rdx; __int64
0x14018fc62  lea     rcx, [rsp+308h+var_250]
0x14018fc6a  mov     [rsp+308h+var_2D0], rcx; __int64
0x14018fc6f  mov     [rsp+308h+var_2D8], eax; int
0x14018fc73  mov     [rsp+308h+var_2E0], edx; int
0x14018fc77  mov     rdx, rbx; int
0x14018fc7a  mov     rcx, rdi; int
0x14018fc7d  call    TxfUpdateTxfDataAttributeMembers
0x14018fc82  cmp     r12w, si
0x14018fc86  jnz     loc_14018FD8C
0x14018fc8c  lea     rdx, [rsp+308h+var_C6]
0x14018fc94  lea     rcx, [rbx+138h]
0x14018fc9b  call    TxfConvertTxfFileIdToMungedName
0x14018fca0  movzx   edx, al
0x14018fca3  mov     [rsp+308h+var_C8], dl
0x14018fcaa  mov     r9, [rbx+140h]
0x14018fcb1  mov     rax, [r9+50h]
0x14018fcb5  mov     rcx, [rax+0B8h]
0x14018fcbc  mov     rax, [rcx+8]
0x14018fcc0  mov     [rsp+308h+var_108], rax
0x14018fcc8  xor     ecx, ecx
0x14018fcca  mov     [rsp+308h+var_C7], cl
0x14018fcd1  mov     [rsp+308h+var_1E8], ecx
0x14018fcd8  mov     [rsp+308h+var_1E0], rcx
0x14018fce0  add     dx, dx
0x14018fce3  mov     [rsp+308h+var_1D8], dx
0x14018fceb  mov     [rsp+308h+var_1D6], dx
0x14018fcf3  lea     rax, [rsp+308h+var_C6]
0x14018fcfb  mov     [rsp+308h+var_1D0], rax
0x14018fd03  mov     [rsp+308h+var_2B0], rcx
0x14018fd08  lea     rax, [rsp+308h+var_1E8]
0x14018fd10  mov     [rsp+308h+var_2B8], rax
0x14018fd15  mov     [rsp+308h+var_2C0], rcx
0x14018fd1a  mov     [rsp+308h+var_2C8], rcx
0x14018fd1f  lea     rax, [rsp+308h+var_28F]
0x14018fd24  mov     [rsp+308h+var_2D0], rax
0x14018fd29  mov     qword ptr [rsp+308h+var_2D8], rcx
0x14018fd2e  lea     rax, [rsp+308h+var_108]
0x14018fd36  mov     qword ptr [rsp+308h+var_2E0], rax
0x14018fd3b  mov     [rsp+308h+var_2E8], rbx
0x14018fd40  mov     r9, [r9+50h]
0x14018fd44  xor     r8d, r8d
0x14018fd47  xor     edx, edx
0x14018fd49  mov     rcx, rdi
0x14018fd4c  call    NtfsAddLink
0x14018fd51  mov     edx, 723h
0x14018fd56  mov     r9d, esi
0x14018fd59  mov     r8, rbx
0x14018fd5c  mov     rcx, rdi
0x14018fd5f  call    NtfsAddStructToRollbackList
0x14018fd64  add     [rax+68h], si
0x14018fd68  add     [rax+6Ah], si
0x14018fd6c  mov     edx, 2
0x14018fd71  or      [rax+4], edx
0x14018fd74  add     [rbx+0BCh], si
0x14018fd7b  add     [rbx+0BEh], si
0x14018fd82  cmp     r12w, si
0x14018fd86  jz      loc_14018FFE5
0x14018fd8c  mov     r12d, [rsp+308h+var_28C]
0x14018fd91  test    r12b, 10h
0x14018fd95  jz      loc_14018FE2B
  ... truncated ...
```
