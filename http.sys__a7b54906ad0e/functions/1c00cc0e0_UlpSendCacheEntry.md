# UlpSendCacheEntry

- ea: `0x1c00cc0e0`
- end: `0x1c00cc797`
- name: `UlpSendCacheEntry`
- size: `1719`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1c00ae070`
- `0x1c00cdcb0`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c000b280`
- `0x1c000f440`
- `0x1c000fc68`
- `0x1c001a4b0`
- `0x1c001a8ac`
- `0x1c001b610`
- `0x1c00456f4`
- `0x1c00510e4`
- `0x1c008f374`
- `0x1c008f3a8`
- `0x1c008f680`
- `0x1c008f76c`
- `0x1c00972f4`
- `0x1c009a2bc`
- `0x1c009a80c`
- `0x1c00adc20`
- `0x1c00c2410`
- `0x1c00cc0e0`
- `0x1c0121978`
- `0x1c012270c`
- `0x1c0123d70`
- `0x1c0129d80`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c00f7131`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00f7148`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00f7131`
- `ntoskrnl!MmSizeOfMdl` at `0x1c00f7148`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c00f72bf`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c00f72bf`
- `ntoskrnl!IoBuildPartialMdl` at `0x1c00cc4eb`
- `ntoskrnl!IoBuildPartialMdl` at `0x1c00cc5c3`
- `ntoskrnl!IoBuildPartialMdl` at `0x1c00cc4eb`
- `ntoskrnl!IoBuildPartialMdl` at `0x1c00cc5c3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00cc374`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f710c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00cc374`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00f710c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f70ca`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00f70ca`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00f71b7`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00f71b7`

## pseudocode

```c
__int64 __fastcall UlpSendCacheEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned int *a6)
{
  unsigned int *v6; // r15
  PSLIST_ENTRY v7; // rbx
  unsigned int v8; // r12d
  int v9; // r10d
  int v11; // r13d
  __int64 v12; // rsi
  unsigned __int8 v13; // r8
  __int64 v14; // r14
  __int64 v15; // rax
  int v16; // edx
  unsigned int v17; // r8d
  int *v18; // rsi
  char *v19; // r10
  int v20; // r9d
  __int64 v21; // r11
  int v22; // esi
  unsigned __int8 v23; // bl
  __int64 v24; // rdx
  unsigned __int32 v25; // eax
  unsigned __int32 v26; // ett
  __int16 v27; // ax
  SIZE_T v28; // r15
  SIZE_T v29; // rbx
  unsigned int v30; // r8d
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // r15
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 (__fastcall *v40)(__int64, __int64, __int64, __int64); // rax
  int v41; // r12d
  __int64 v42; // r13
  struct _MDL *v43; // r15
  __int64 v44; // r10
  __int64 v45; // r8
  unsigned __int64 v46; // r9
  unsigned __int64 v47; // rcx
  int v48; // edx
  __int64 v49; // r9
  unsigned int v50; // eax
  __int64 v51; // r10
  __int64 v52; // r9
  unsigned __int64 v53; // r8
  int v54; // edx
  __int64 v55; // rax
  int v56; // edx
  struct _SLIST_ENTRY *v57; // rax
  const char *v58; // r15
  int v59; // esi
  __int64 v60; // rcx
  __int64 v61; // r13
  int v62; // eax
  ULONG_PTR v63; // rdx
  bool v64; // sf
  __int64 v66; // r9
  __int64 v67; // rbx
  unsigned int v68; // r8d
  unsigned int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rax
  SIZE_T v72; // rbx
  __int64 v73; // r15
  unsigned __int64 v74; // rax
  char *PoolWithTagPriority; // rax
  __int64 v76; // r9
  __int64 v77; // rdx
  struct _SLIST_ENTRY *v78; // rcx
  char *v79; // rdx
  __int64 v80; // r10
  struct _SLIST_ENTRY *Next; // r9
  unsigned __int64 v82; // rdx
  __int64 v83; // r8
  __int64 RangeCacheTracker; // rax
  int v85; // eax
  struct _SLIST_ENTRY *v86; // rax
  __int16 v87; // ax
  __int64 v88; // r9
  int v89; // eax
  __int64 v90; // [rsp+28h] [rbp-D8h]
  __int64 v91; // [rsp+30h] [rbp-D0h]
  unsigned int v92; // [rsp+50h] [rbp-B0h]
  unsigned int v93; // [rsp+50h] [rbp-B0h]
  __int64 v94; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v95; // [rsp+68h] [rbp-98h]
  __int128 v96; // [rsp+70h] [rbp-90h]
  __int64 v97; // [rsp+80h] [rbp-80h]
  __int64 v98; // [rsp+88h] [rbp-78h]
  __int64 v99; // [rsp+90h] [rbp-70h] BYREF
  __int64 v100; // [rsp+98h] [rbp-68h]
  __int128 v101; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v102[3]; // [rsp+B0h] [rbp-50h] BYREF
  char v103; // [rsp+C8h] [rbp-38h]
  int v104; // [rsp+C9h] [rbp-37h]
  __int16 v105; // [rsp+CDh] [rbp-33h]
  char v106; // [rsp+CFh] [rbp-31h]
  char v107; // [rsp+D0h] [rbp-30h]
  char v108; // [rsp+D1h] [rbp-2Fh] BYREF
  _BYTE v109[24]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = a6;
  v7 = 0;
  v99 = 0;
  v8 = 0;
  LODWORD(v94) = 0;
  v9 = a4;
  v98 = 0;
  v95 = a4;
  v11 = a2;
  v12 = a1;
  v100 = a1;
  v13 = a5;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    if ( a1 )
      v66 = *(_QWORD *)(a1 + 24);
    else
      v66 = 0;
    v90 = a3;
    WPP_SF_qiLqqlq(a1, a2, a1, v66, a2);
    v13 = a5;
    v9 = v95;
  }
  *a6 = 0;
  if ( (*(_DWORD *)(v12 + 520) & 2) != 0 )
  {
    v41 = -1073741247;
    goto LABEL_73;
  }
  v14 = *(_QWORD *)(v12 + 456);
  if ( *(_BYTE *)(v14 + 3502) )
  {
    v8 = *(_DWORD *)(a3 + 640);
    if ( *(_DWORD *)(v14 + 2660) )
    {
      if ( !*(_BYTE *)(v14 + 2688) )
        v8 += 2;
    }
  }
  if ( *(_DWORD *)(v14 + 2660) > 1u && *(_WORD *)(a3 + 116) == 200 && !*(_BYTE *)(v14 + 2688) )
  {
    v41 = UlSendMultiRangeFromFlatCache(a3, v14, v11, v9, (__int64)a6);
LABEL_71:
    v64 = v41 < 0;
    goto LABEL_72;
  }
  if ( *(_BYTE *)(a3 + 114)
    || ((v15 = *(_QWORD *)(a3 + 8)) == 0 ? (v16 = 0) : (v16 = *(_DWORD *)(v15 + 104)),
        (a1 = *(unsigned __int16 *)(a3 + 116), (v11 & 2) != 0)
     || (v11 & 0x40) != 0
     || (unsigned __int16)(a1 - 100) <= 0x63u
     || (_WORD)a1 == 204
     || (_WORD)a1 == 304
     || v16 == 5) )
  {
    v109[0] = 0;
    v22 = 0;
  }
  else
  {
    v17 = *(_DWORD *)(a3 + 516);
    v18 = (int *)v109;
    v107 = 0;
    v19 = &v108;
    v20 = 1;
    do
    {
      v21 = v20++;
      *v19++ = v17 % 0xA + 48;
      v17 /= 0xAu;
    }
    while ( v17 );
    a1 = v21;
    if ( (int)v21 >= 0 )
    {
      do
      {
        *(_BYTE *)v18 = *(&v107 + a1);
        v18 = (int *)((char *)v18 + 1);
        --a1;
      }
      while ( a1 >= 0 );
    }
    v13 = a5;
    v22 = (_DWORD)v18 - 1 - (unsigned int)v109;
  }
  v23 = v11 & 1;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    WPP_SF_qqD(144, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, v14, *(_QWORD *)(v14 + 64), v23);
    v13 = a5;
  }
  v24 = *(unsigned int *)(v14 + 2728);
  v92 = v24;
  if ( (_DWORD)v24 == 3 )
  {
    _m_prefetchw((const void *)(v14 + 2188));
    v25 = *(_DWORD *)(v14 + 2188);
    do
    {
      a1 = v25;
      v26 = v25;
      v25 = _InterlockedCompareExchange((volatile signed __int32 *)(v14 + 2188), v25, v25);
    }
    while ( v26 != v25 );
    if ( (v25 & 1) == 0 )
    {
      v27 = *(_WORD *)(v14 + 2096);
      if ( v23 )
      {
        if ( v27 || !*(_WORD *)(v14 + 2098) )
        {
          v24 = 1;
LABEL_28:
          v92 = v24;
          goto LABEL_29;
        }
      }
      else if ( v27 == 1 && !*(_WORD *)(v14 + 2098) )
      {
        v24 = 2;
        goto LABEL_28;
      }
    }
    v24 = 0;
    goto LABEL_28;
  }
LABEL_29:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    WPP_SF_D(145, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids);
    v13 = a5;
  }
  v28 = *(unsigned int *)(a3 + 516);
  v29 = *(unsigned int *)(a3 + 512);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    LODWORD(v90) = v8;
    WPP_SF_LLlL(a1, v24, (unsigned int)v29, (unsigned int)v28, v13);
  }
  if ( v8 )
    v8 += UlH3ExtraHeaderCount;
  if ( (unsigned int)v29 <= 0x200 && (unsigned int)v28 <= 0x40000 && v8 <= 0x14 )
  {
    if ( UxCompactMode )
    {
      v67 = qword_1C00741B0;
      v68 = KeGetCurrentNodeNumber() + 1;
      v69 = *(_DWORD *)v67 - 1;
      if ( v68 < *(_DWORD *)v67 )
        v69 = v68;
      v70 = v69;
      v71 = *(_QWORD *)(v67 + 32);
      v34 = *(_QWORD *)(v71 + 8 * v70);
      if ( !*(_BYTE *)(v34 + 112) )
        PplpLazyInitializeLookasideList(v67, *(_QWORD *)(v71 + 8 * v70));
      ++*(_DWORD *)(v34 + 20);
      v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34);
      if ( v7 )
        goto LABEL_45;
    }
    else
    {
      v30 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v31 = *(_DWORD *)qword_1C00741B0 - 1;
      if ( v30 < *(_DWORD *)qword_1C00741B0 )
        v31 = v30;
      v32 = v31;
      v33 = *(_QWORD *)(qword_1C00741B0 + 32);
      v34 = *(_QWORD *)(v33 + 8 * v32);
      if ( !*(_BYTE *)(v34 + 112) )
        PplpLazyInitializeLookasideList(qword_1C00741B0, *(_QWORD *)(v33 + 8 * v32));
      ++*(_DWORD *)(v34 + 20);
      v7 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34);
      if ( v7 )
        goto LABEL_45;
    }
    v37 = *(unsigned int *)(v34 + 40);
    v38 = *(unsigned int *)(v34 + 44);
    v39 = *(unsigned int *)(v34 + 36);
    v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v34 + 48);
    ++*(_DWORD *)(v34 + 24);
    v7 = (PSLIST_ENTRY)v40(v39, v38, v37, v34);
LABEL_45:
    if ( v7 )
    {
      LODWORD(v7[1].Next) = 1094937685;
      BYTE5(v7[1].Next) = a5;
      *((_QWORD *)&v7[8].Next + 1) = 0;
      v7[9].Next = 0;
      LODWORD(v7[11].Next) = 0;
      BYTE4(v7[1].Next) = 1;
      LODWORD(v7[12].Next) = 0;
      *((_DWORD *)&v7[12].Next + 3) = 0;
      v7[2].Next = 0;
      v7[3].Next = 0;
      v7[4].Next = 0;
      UxDuoInitializeCollection(&v7[13].Next + 1);
    }
    goto LABEL_47;
  }
  v72 = MmSizeOfMdl((PVOID)0xFFF, v29);
  v73 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, v28) + 7) & 0xFFFFFFF8;
  v36 = (v72 + 7) & 0xFFFFFFF8;
  v97 = v36;
  v35 = v73 + (unsigned int)UlVariableHeadersMdlLength + 24LL * v8 + (unsigned int)UlVariableHeaderSize;
  v74 = v35 + v36 + 640;
  if ( v74 <= 0xFFFFFFFF )
  {
    PoolWithTagPriority = (char *)ExAllocatePoolWithTagPriority(
                                    (POOL_TYPE)512,
                                    (unsigned int)v74,
                                    0x41436C55u,
                                    LowPoolPriority);
    v7 = (PSLIST_ENTRY)PoolWithTagPriority;
    if ( PoolWithTagPriority )
    {
      strcpy(PoolWithTagPriority + 16, "UlCA");
      *((_QWORD *)PoolWithTagPriority + 17) = 0;
      *((_QWORD *)PoolWithTagPriority + 18) = 0;
      *((_DWORD *)PoolWithTagPriority + 44) = 0;
      *((_DWORD *)PoolWithTagPriority + 48) = 0;
      *((_DWORD *)PoolWithTagPriority + 51) = 0;
      *((_QWORD *)PoolWithTagPriority + 4) = 0;
      *((_QWORD *)PoolWithTagPriority + 6) = 0;
      *((_QWORD *)PoolWithTagPriority + 8) = 0;
      PoolWithTagPriority[21] = a5;
      UxDuoInitializeCollection(PoolWithTagPriority + 216);
      v76 = (unsigned int)UlVariableHeaderSize;
      v77 = (unsigned int)UlVariableHeadersMdlLength;
      v78 = (PSLIST_ENTRY)((char *)v7 + v97 + 640);
      *((_QWORD *)&v7[6].Next + 1) = v7 + 40;
      v79 = (char *)v78 + v77;
      v7[7].Next = v78;
      *((_QWORD *)&v7[7].Next + 1) = v79;
      *((_DWORD *)&v7[5].Next + 2) = v76;
      v7[6].Next = (struct _SLIST_ENTRY *)&v79[v73];
      UlInitializeParsedHeaders(&v7[11].Next + 1, &v79[v73 + v76], v8);
      v80 = *((unsigned int *)&v7[5].Next + 2);
      Next = v7[7].Next;
      v82 = (unsigned __int64)v7[6].Next & 0xFFFFFFFFFFFFF000uLL;
      v83 = (__int64)v7[6].Next & 0xFFF;
      Next->Next = 0;
      *((_WORD *)&Next->Next + 4) = 8 * (((unsigned __int64)(v80 + v83 + 4095) >> 12) + 6);
      *((_WORD *)&Next->Next + 5) = 0;
      Next[2].Next = (struct _SLIST_ENTRY *)v82;
      *((_DWORD *)&Next[2].Next + 3) = v83;
      *((_DWORD *)&Next[2].Next + 2) = v80;
      MmBuildMdlForNonPagedPool((PMDL)v7[7].Next);
    }
  }
  else
  {
    v7 = 0;
  }
LABEL_47:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_q(108, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, v7);
  if ( !v7 )
  {
LABEL_124:
    v41 = -1073741670;
    goto LABEL_125;
  }
  v41 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v14 + 48));
  v7[5].Next = (struct _SLIST_ENTRY *)a3;
  v7[8].Next = (struct _SLIST_ENTRY *)v14;
  *((_DWORD *)&v7[9].Next + 2) = v11;
  if ( !*(_BYTE *)(v14 + 3502) )
  {
    v42 = v98;
    goto LABEL_52;
  }
  v42 = (__int64)(&v7[11].Next + 1);
  v41 = UlCopyParsedHeaders(&v7[11].Next + 1, a3 + 632);
  if ( v41 >= 0 )
  {
LABEL_52:
    v43 = *(struct _MDL **)(a3 + 520);
    if ( *(_DWORD *)(v14 + 2660) != 1 || *(_WORD *)(a3 + 116) != 200 || *(_BYTE *)(v14 + 2688) )
    {
      if ( !*(_BYTE *)(v14 + 3502) )
      {
        v44 = *(unsigned int *)(a3 + 512);
        v45 = *((_QWORD *)&v7[6].Next + 1);
        v46 = ((unsigned __int64)v43->StartVa + v43->ByteOffset + (unsigned __int64)*(unsigned int *)(a3 + 516))
            & 0xFFFFFFFFFFFFF000uLL;
        v47 = ((LOWORD(v43->StartVa) + (unsigned __int16)v43->ByteOffset + (unsigned __int16)*(_DWORD *)(a3 + 516))
             & 0xFFF)
            + v44
            + 4095;
        v48 = (LOWORD(v43->StartVa) + (unsigned __int16)v43->ByteOffset + (unsigned __int16)*(_DWORD *)(a3 + 516))
            & 0xFFF;
        *(_QWORD *)v45 = 0;
        *(_WORD *)(v45 + 10) = 0;
        *(_QWORD *)(v45 + 32) = v46;
        *(_DWORD *)(v45 + 44) = v48;
        *(_DWORD *)(v45 + 40) = v44;
        *(_WORD *)(v45 + 8) = 8 * ((v47 >> 12) + 6);
        IoBuildPartialMdl(
          v43,
          *((PMDL *)&v7[6].Next + 1),
          (char *)v43->StartVa + v43->ByteOffset + (unsigned __int64)*(unsigned int *)(a3 + 516),
          *(_DWORD *)(a3 + 512));
      }
      LOBYTE(v35) = 1;
      UlGenerateVariableHeaders(v92, v35, (int)v109, v22, v7[6].Next, v90, v42, 0, (__int64)&v94, (__int64)&v99);
      *((_DWORD *)&v7[7].Next[2].Next + 2) = v94;
      **((_QWORD **)&v7[6].Next + 1) = v7[7].Next;
      v50 = *(_DWORD *)(a3 + 516);
      v51 = v50;
      if ( v50 )
      {
        v52 = *((_QWORD *)&v7[7].Next + 1);
        v53 = ((unsigned __int64)v43->StartVa + v43->ByteOffset) & 0xFFFFFFFFFFFFF000uLL;
        v54 = (LOWORD(v43->StartVa) + (unsigned __int16)v43->ByteOffset) & 0xFFF;
        v55 = (LOWORD(v43->StartVa) + (unsigned __int16)v43->ByteOffset) & 0xFFF;
        *(_QWORD *)v52 = 0;
        *(_WORD *)(v52 + 10) = 0;
        *(_QWORD *)(v52 + 32) = v53;
        *(_DWORD *)(v52 + 44) = v54;
        *(_DWORD *)(v52 + 40) = v51;
        *(_WORD *)(v52 + 8) = 8 * (((unsigned __int64)(v55 + v51 + 4095) >> 12) + 6);
        IoBuildPartialMdl(
          v43,
          *((PMDL *)&v7[7].Next + 1),
          (char *)v43->StartVa + v43->ByteOffset,
          *(_DWORD *)(a3 + 516));
        v7[7].Next->Next = (struct _SLIST_ENTRY *)*((_QWORD *)&v7[7].Next + 1);
      }
      else
      {
        v7[7].Next->Next = 0;
      }
      *((_DWORD *)&v7[34].Next + 2) = 3;
      if ( *(_BYTE *)(v14 + 3502) )
      {
        if ( *(_DWORD *)(a3 + 516) )
        {
          v86 = (struct _SLIST_ENTRY *)*((_QWORD *)&v7[7].Next + 1);
          LODWORD(v7[11].Next) = 0;
          v7[35].Next = v86;
          *a6 = *(_DWORD *)(a3 + 516);
        }
      }
      else
      {
        v56 = v94 + *(_DWORD *)(a3 + 512);
        v57 = (struct _SLIST_ENTRY *)*((_QWORD *)&v7[6].Next + 1);
        LODWORD(v7[11].Next) = v56;
        v7[35].Next = v57;
        *a6 = v56 + *(_DWORD *)(a3 + 516);
      }
LABEL_59:
      if ( *(_BYTE *)(a3 + 576) && v95 )
        *((_QWORD *)&v7[8].Next + 1) = v95;
      v58 = "NULL";
      v59 = *(_DWORD *)(a3 + 512) + *(_DWORD *)(a3 + 516);
      v60 = *(_QWORD *)(a3 + 192);
      v93 = 4;
      if ( v60 && *(_DWORD *)(a3 + 188) )
      {
        v58 = *(const char **)(a3 + 192);
        v93 = *(_DWORD *)(a3 + 188);
      }
      v61 = v100;
      if ( *(_BYTE *)(*(_QWORD *)(v100 + 960) + 1568LL) )
      {
        v102[2] = *(_QWORD *)(v100 + 960);
        v102[0] = v14 + 72;
        v91 = *(_QWORD *)(v14 + 56);
        v62 = *(_DWORD *)(a3 + 312);
        v104 = 0;
        v105 = 0;
        v102[1] = 0;
        v106 = 0;
        v103 = 0;
        McTemplateK0pqqxs_UlEtwWriteEventWrapper(
          v60,
          (unsigned int)HTTP_EVENT_SERVED_FROM_CACHE_LEGACY_V1,
          (unsigned int)v102,
          v14,
          v62,
          v59,
          v91,
          (__int64)v58);
      }
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000) != 0 )
      {
        v87 = v93;
        v88 = *(_QWORD *)(v14 + 56);
        *((_QWORD *)&v96 + 1) = v58;
        if ( v93 > 0x1F40 )
          v87 = 8000;
        LOWORD(v96) = v87;
        WORD1(v96) = v87;
        v89 = *(_DWORD *)(a3 + 312);
        DWORD1(v96) = 0;
        v101 = v96;
        WPP_SF_qiLL_CTDSTR_(
          96,
          (unsigned int)WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids,
          v14,
          v88,
          v89,
          v59,
          (__int64)&v101);
      }
      v63 = (ULONG_PTR)&v7[2];
      if ( v7[2].Next || v7[3].Next || v7[4].Next )
        UlBugCheckEx(1u, v63, (ULONG_PTR)"minio\\http\\sys\\sendresponse.c", 0x19EAu);
      LODWORD(v90) = -1;
      LOBYTE(v49) = 1;
      UlThreadPoolEnqueueWorkItem(0, v63, UlSendCacheEntryWorker, v49, *(_QWORD *)(v61 + 952), v90);
      v6 = a6;
      goto LABEL_71;
    }
    LOBYTE(v36) = *(_BYTE *)(a3 + 552) == 0;
    RangeCacheTracker = UlFastCreateRangeCacheTracker(*(_QWORD *)(v14 + 2664), v35, *(_DWORD *)(a3 + 516), v36, v42);
    if ( RangeCacheTracker )
    {
      v6 = a6;
      v7[9].Next = (struct _SLIST_ENTRY *)RangeCacheTracker;
      if ( *(_BYTE *)(v14 + 3502) )
      {
        v85 = UlBuildParsedHeaderFastRangeResponse(v7, a3, v92, v14, a6);
      }
      else
      {
        HIDWORD(v90) = HIDWORD(a6);
        v85 = UlBuildFastRangeCacheMdlChain(v7, a3, v92, *(_QWORD *)(v14 + 2664));
      }
      v41 = v85;
      v64 = v85 < 0;
      if ( v85 )
      {
LABEL_72:
        if ( !v64 )
          goto LABEL_73;
        goto LABEL_126;
      }
      goto LABEL_59;
    }
    goto LABEL_124;
  }
LABEL_125:
  v6 = a6;
LABEL_126:
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 48), 0xFFFFFFFF) == 1 )
      UlpQueueFreeHttpRequest(v14);
    UlFreeCacheTracker(v7);
  }
LABEL_73:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_DD(97, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, *v6, (unsigned int)v41);
  return (unsigned int)v41;
}

```

## disassembly

```asm
0x1c00cc0e0  push    rbp
0x1c00cc0e2  push    rbx
0x1c00cc0e3  push    rsi
0x1c00cc0e4  push    rdi
0x1c00cc0e5  push    r12
0x1c00cc0e7  push    r13
0x1c00cc0e9  push    r14
0x1c00cc0eb  push    r15
0x1c00cc0ed  lea     rbp, [rsp-8]
0x1c00cc0f2  sub     rsp, 108h
0x1c00cc0f9  mov     rax, cs:__security_cookie
0x1c00cc100  xor     rax, rsp
0x1c00cc103  mov     [rbp+40h+var_48], rax
0x1c00cc107  mov     r15, [rbp+40h+arg_28]
0x1c00cc10b  xor     r14d, r14d
0x1c00cc10e  mov     [rsp+140h+var_E8], r15
0x1c00cc113  mov     ebx, r14d
0x1c00cc116  mov     [rbp+40h+var_B0], r14
0x1c00cc11a  mov     r12d, r14d
0x1c00cc11d  mov     dword ptr [rsp+140h+var_E0], r14d
0x1c00cc122  mov     r10, r9
0x1c00cc125  mov     [rbp+40h+var_B8], r14
0x1c00cc129  mov     rdi, r8
0x1c00cc12c  mov     [rsp+140h+var_D8], r9
0x1c00cc131  mov     r13d, edx
0x1c00cc134  mov     rsi, rcx
0x1c00cc137  mov     [rbp+40h+var_A8], rcx
0x1c00cc13b  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cc145  movzx   r8d, [rbp+40h+arg_20]
0x1c00cc14a  jnz     loc_1C00F6F6A
0x1c00cc150  mov     [r15], r14d
0x1c00cc153  mov     eax, [rsi+208h]
0x1c00cc159  test    al, 2
0x1c00cc15b  jnz     loc_1C00F6FA8
0x1c00cc161  mov     r14, [rsi+1C8h]
0x1c00cc168  cmp     [r14+0DAEh], bl
0x1c00cc16f  jnz     loc_1C00F6FB3
0x1c00cc175  cmp     dword ptr [r14+0A64h], 1
0x1c00cc17d  mov     eax, 0C8h
0x1c00cc182  ja      loc_1C00F6FDD
0x1c00cc188  cmp     [rdi+72h], bl
0x1c00cc18b  jnz     loc_1C00F701B
0x1c00cc191  mov     rax, [rdi+8]
0x1c00cc195  test    rax, rax
0x1c00cc198  jz      loc_1C00F7012
0x1c00cc19e  mov     edx, [rax+68h]
0x1c00cc1a1  movzx   ecx, word ptr [rdi+74h]
0x1c00cc1a5  test    r13b, 2
0x1c00cc1a9  jnz     loc_1C00F701B
0x1c00cc1af  test    r13b, 40h
0x1c00cc1b3  jnz     loc_1C00F701B
0x1c00cc1b9  lea     eax, [rcx-64h]
0x1c00cc1bc  cmp     ax, 63h ; 'c'
0x1c00cc1c0  jbe     loc_1C00F701B
0x1c00cc1c6  mov     eax, 0CCh
0x1c00cc1cb  cmp     cx, ax
0x1c00cc1ce  jz      loc_1C00F701B
0x1c00cc1d4  mov     eax, 130h
0x1c00cc1d9  cmp     cx, ax
0x1c00cc1dc  jz      loc_1C00F701B
0x1c00cc1e2  cmp     edx, 5
0x1c00cc1e5  jz      loc_1C00F701B
0x1c00cc1eb  mov     r8d, [rdi+204h]
0x1c00cc1f2  lea     rsi, [rbp+40h+var_60]
0x1c00cc1f6  mov     [rbp+40h+var_70], bl
0x1c00cc1f9  lea     r10, [rbp+40h+var_6F]
0x1c00cc1fd  mov     r9d, 1
0x1c00cc203  mov     eax, 0CCCCCCCDh
0x1c00cc208  movsxd  r11, r9d
0x1c00cc20b  mul     r8d
0x1c00cc20e  inc     r9d
0x1c00cc211  lea     r10, [r10+1]
0x1c00cc215  shr     edx, 3
0x1c00cc218  movzx   eax, dl
0x1c00cc21b  shl     al, 2
0x1c00cc21e  lea     ecx, [rax+rdx]
0x1c00cc221  add     cl, cl
0x1c00cc223  sub     r8b, cl
0x1c00cc226  add     r8b, 30h ; '0'
0x1c00cc22a  mov     [r10-1], r8b
0x1c00cc22e  mov     r8d, edx
0x1c00cc231  test    edx, edx
0x1c00cc233  jnz     short loc_1C00CC203
0x1c00cc235  mov     rcx, r11
0x1c00cc238  test    r11d, r11d
0x1c00cc23b  js      short loc_1C00CC250
0x1c00cc23d  nop     dword ptr [rax]
0x1c00cc240  movzx   eax, [rbp+rcx+40h+var_70]
0x1c00cc245  mov     [rsi], al
0x1c00cc247  inc     rsi
0x1c00cc24a  sub     rcx, 1
0x1c00cc24e  jns     short loc_1C00CC240
0x1c00cc250  movzx   r8d, [rbp+40h+arg_20]
0x1c00cc255  lea     rax, [rbp+40h+var_60]
0x1c00cc259  dec     rsi
0x1c00cc25c  sub     esi, eax
0x1c00cc25e  xor     r9d, r9d
0x1c00cc261  movzx   ebx, r13b
0x1c00cc265  and     bl, 1
0x1c00cc268  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cc272  jnz     loc_1C00F7029
0x1c00cc278  mov     edx, [r14+0AA8h]
0x1c00cc27f  mov     [rsp+140h+var_F0], edx
0x1c00cc283  cmp     edx, 3
0x1c00cc286  jnz     short loc_1C00CC2CF
0x1c00cc288  prefetchw byte ptr [r14+88Ch]
0x1c00cc290  mov     eax, [r14+88Ch]
0x1c00cc297  mov     ecx, eax
0x1c00cc299  lock cmpxchg [r14+88Ch], ecx
0x1c00cc2a2  jnz     short loc_1C00CC297
0x1c00cc2a4  test    al, 1
0x1c00cc2a6  jnz     loc_1C00CC783
0x1c00cc2ac  movzx   eax, word ptr [r14+830h]
0x1c00cc2b4  test    bl, bl
0x1c00cc2b6  jz      loc_1C00CC76E
0x1c00cc2bc  cmp     ax, 1
0x1c00cc2c0  jb      loc_1C00F7055
0x1c00cc2c6  mov     edx, 1
0x1c00cc2cb  mov     [rsp+140h+var_F0], edx
0x1c00cc2cf  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cc2d9  jnz     loc_1C00F707B
0x1c00cc2df  mov     r15d, [rdi+204h]
0x1c00cc2e6  mov     ebx, [rdi+200h]
0x1c00cc2ec  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cc2f6  jnz     loc_1C00F7099
0x1c00cc2fc  test    r12d, r12d
0x1c00cc2ff  jnz     loc_1C00F70B7
0x1c00cc305  cmp     ebx, 200h
0x1c00cc30b  ja      loc_1C00F7129
0x1c00cc311  cmp     r15d, 40000h
0x1c00cc318  ja      loc_1C00F7129
0x1c00cc31e  cmp     r12d, 14h
0x1c00cc322  ja      loc_1C00F7129
0x1c00cc328  cmp     cs:UxCompactMode, 0
0x1c00cc32f  jnz     loc_1C00F70C3
0x1c00cc335  mov     eax, gs:1A4h
0x1c00cc33d  mov     rcx, cs:qword_1C00741B0
0x1c00cc344  lea     r8d, [rax+1]
0x1c00cc348  mov     edx, [rcx]
0x1c00cc34a  cmp     r8d, edx
0x1c00cc34d  lea     eax, [rdx-1]
0x1c00cc350  cmovb   eax, r8d
0x1c00cc354  mov     edx, eax
0x1c00cc356  mov     rax, [rcx+20h]
0x1c00cc35a  mov     r15, [rax+rdx*8]
0x1c00cc35e  cmp     byte ptr [r15+70h], 0
0x1c00cc363  jnz     short loc_1C00CC36D
0x1c00cc365  mov     rdx, r15
0x1c00cc368  call    PplpLazyInitializeLookasideList
0x1c00cc36d  inc     dword ptr [r15+14h]
0x1c00cc371  mov     rcx, r15; ListHead
0x1c00cc374  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00cc37b  nop     dword ptr [rax+rax+00h]
0x1c00cc380  mov     rbx, rax
0x1c00cc383  test    rax, rax
0x1c00cc386  jnz     short loc_1C00CC3A8
0x1c00cc388  mov     r8d, [r15+28h]
0x1c00cc38c  mov     r9, r15
0x1c00cc38f  mov     edx, [r15+2Ch]
0x1c00cc393  mov     ecx, [r15+24h]
0x1c00cc397  mov     rax, [r15+30h]
0x1c00cc39b  inc     dword ptr [r15+18h]
0x1c00cc39f  call    cs:__guard_dispatch_icall_fptr
0x1c00cc3a5  mov     rbx, rax
0x1c00cc3a8  xor     r15d, r15d
0x1c00cc3ab  test    rbx, rbx
0x1c00cc3ae  jz      short loc_1C00CC3FD
0x1c00cc3b0  movzx   eax, [rbp+40h+arg_20]
0x1c00cc3b4  lea     rcx, [rbx+0D8h]
0x1c00cc3bb  mov     dword ptr [rbx+10h], 41436C55h
0x1c00cc3c2  mov     [rbx+15h], al
0x1c00cc3c5  mov     [rbx+88h], r15
0x1c00cc3cc  mov     [rbx+90h], r15
0x1c00cc3d3  mov     [rbx+0B0h], r15d
0x1c00cc3da  mov     byte ptr [rbx+14h], 1
0x1c00cc3de  mov     [rbx+0C0h], r15d
0x1c00cc3e5  mov     [rbx+0CCh], r15d
0x1c00cc3ec  mov     [rbx+20h], r15
0x1c00cc3f0  mov     [rbx+30h], r15
0x1c00cc3f4  mov     [rbx+40h], r15
0x1c00cc3f8  call    UxDuoInitializeCollection
0x1c00cc3fd  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cc407  jnz     loc_1C00F72D9
0x1c00cc40d  test    rbx, rbx
0x1c00cc410  jz      loc_1C00F7472
0x1c00cc416  mov     r12d, r15d
0x1c00cc419  lock inc dword ptr [r14+30h]
0x1c00cc41e  mov     [rbx+50h], rdi
0x1c00cc422  mov     [rbx+80h], r14
0x1c00cc429  mov     [rbx+98h], r13d
0x1c00cc430  cmp     byte ptr [r14+0DAEh], 0
0x1c00cc438  jnz     loc_1C00F72F3
0x1c00cc43e  mov     r13, [rbp+40h+var_B8]
0x1c00cc442  cmp     dword ptr [r14+0A64h], 1
0x1c00cc44a  mov     r15, [rdi+208h]
0x1c00cc451  jz      loc_1C00F7319
0x1c00cc457  cmp     byte ptr [r14+0DAEh], 0
0x1c00cc45f  jnz     loc_1C00CC4F7
0x1c00cc465  mov     eax, [r15+2Ch]
0x1c00cc469  xor     r11d, r11d
0x1c00cc46c  mov     r9d, [rdi+204h]
0x1c00cc473  mov     r10d, [rdi+200h]
0x1c00cc47a  add     r9, rax
0x1c00cc47d  add     r9, [r15+20h]
0x1c00cc481  mov     r8, [rbx+68h]
0x1c00cc485  mov     edx, r9d
0x1c00cc488  mov     eax, edx
0x1c00cc48a  and     r9, 0FFFFFFFFFFFFF000h
0x1c00cc491  and     eax, 0FFFh
0x1c00cc496  lea     rcx, [r10+0FFFh]
0x1c00cc49d  add     rcx, rax
0x1c00cc4a0  and     edx, 0FFFh
0x1c00cc4a6  mov     [r8], r11
0x1c00cc4a9  mov     [r8+0Ah], r11w
0x1c00cc4ae  mov     [r8+20h], r9
0x1c00cc4b2  mov     [r8+2Ch], edx
0x1c00cc4b6  mov     [r8+28h], r10d
0x1c00cc4ba  shr     rcx, 0Ch
0x1c00cc4be  add     cx, 6
0x1c00cc4c2  shl     cx, 3
0x1c00cc4c6  mov     [r8+8], cx
0x1c00cc4cb  mov     rcx, r15; SourceMdl
0x1c00cc4ce  mov     r8d, [rdi+204h]
0x1c00cc4d5  mov     eax, [r15+2Ch]
0x1c00cc4d9  mov     r9d, [rdi+200h]; Length
0x1c00cc4e0  add     r8, rax
0x1c00cc4e3  add     r8, [r15+20h]; VirtualAddress
0x1c00cc4e7  mov     rdx, [rbx+68h]; TargetMdl
0x1c00cc4eb  call    cs:__imp_IoBuildPartialMdl
0x1c00cc4f2  nop     dword ptr [rax+rax+00h]
0x1c00cc4f7  xor     ecx, ecx
0x1c00cc4f9  lea     rax, [rbp+40h+var_B0]
0x1c00cc4fd  mov     [rsp+140h+var_F8], rax; __int64
0x1c00cc502  lea     r8, [rbp+40h+var_60]; int
0x1c00cc506  lea     rax, [rsp+140h+var_E0]
0x1c00cc50b  mov     r9d, esi; int
0x1c00cc50e  mov     [rsp+140h+var_100], rax; __int64
0x1c00cc513  mov     dl, 1; int
0x1c00cc515  mov     rax, [rbx+60h]
0x1c00cc519  mov     [rsp+140h+var_108], rcx; __int64
0x1c00cc51e  mov     ecx, [rsp+140h+var_F0]; int
0x1c00cc522  mov     [rsp+140h+var_110], r13; __int64
0x1c00cc527  mov     [rsp+140h+var_120], rax; void *
0x1c00cc52c  call    UlGenerateVariableHeaders
0x1c00cc531  mov     rcx, [rbx+70h]
0x1c00cc535  mov     eax, dword ptr [rsp+140h+var_E0]
0x1c00cc539  mov     [rcx+28h], eax
0x1c00cc53c  mov     rax, [rbx+70h]
0x1c00cc540  mov     rcx, [rbx+68h]
0x1c00cc544  mov     [rcx], rax
0x1c00cc547  mov     eax, [rdi+204h]
0x1c00cc54d  mov     r10d, eax
0x1c00cc550  test    eax, eax
0x1c00cc552  jz      loc_1C00F73B6
0x1c00cc558  mov     r8d, [r15+2Ch]
0x1c00cc55c  lea     rcx, [r10+0FFFh]
0x1c00cc563  add     r8, [r15+20h]
0x1c00cc567  xor     r11d, r11d
0x1c00cc56a  mov     r9, [rbx+78h]
0x1c00cc56e  mov     edx, r8d
0x1c00cc571  mov     eax, edx
0x1c00cc573  and     r8, 0FFFFFFFFFFFFF000h
0x1c00cc57a  and     edx, 0FFFh
0x1c00cc580  and     eax, 0FFFh
0x1c00cc585  add     rcx, rax
0x1c00cc588  mov     [r9], r11
0x1c00cc58b  mov     [r9+0Ah], r11w
0x1c00cc590  mov     [r9+20h], r8
0x1c00cc594  mov     [r9+2Ch], edx
0x1c00cc598  mov     [r9+28h], r10d
0x1c00cc59c  shr     rcx, 0Ch
0x1c00cc5a0  add     cx, 6
0x1c00cc5a4  shl     cx, 3
0x1c00cc5a8  mov     [r9+8], cx
0x1c00cc5ad  mov     rcx, r15; SourceMdl
0x1c00cc5b0  mov     r8d, [r15+2Ch]
0x1c00cc5b4  add     r8, [r15+20h]; VirtualAddress
0x1c00cc5b8  mov     r9d, [rdi+204h]; Length
0x1c00cc5bf  mov     rdx, [rbx+78h]; TargetMdl
0x1c00cc5c3  call    cs:__imp_IoBuildPartialMdl
0x1c00cc5ca  nop     dword ptr [rax+rax+00h]
0x1c00cc5cf  mov     rcx, [rbx+70h]
0x1c00cc5d3  xor     r8d, r8d
0x1c00cc5d6  mov     rax, [rbx+78h]
0x1c00cc5da  mov     [rcx], rax
0x1c00cc5dd  mov     dword ptr [rbx+228h], 3
0x1c00cc5e7  cmp     byte ptr [r14+0DAEh], 0
0x1c00cc5ef  jnz     loc_1C00F73C5
0x1c00cc5f5  mov     edx, [rdi+200h]
0x1c00cc5fb  add     edx, dword ptr [rsp+140h+var_E0]
0x1c00cc5ff  mov     rax, [rbx+68h]
0x1c00cc603  mov     [rbx+0B0h], edx
0x1c00cc609  mov     [rbx+230h], rax
0x1c00cc610  mov     ecx, [rdi+204h]
0x1c00cc616  add     ecx, edx
0x1c00cc618  mov     rdx, [rsp+140h+var_E8]
0x1c00cc61d  mov     [rdx], ecx
0x1c00cc61f  cmp     byte ptr [rdi+240h], 0
0x1c00cc626  jnz     loc_1C00F73F6
0x1c00cc62c  mov     esi, [rdi+204h]
  ... truncated ...
```
