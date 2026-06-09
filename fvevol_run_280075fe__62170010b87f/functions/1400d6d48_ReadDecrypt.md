# ReadDecrypt

- ea: `0x1400d6d48`
- end: `0x1400d776d`
- name: `ReadDecrypt`
- size: `2597`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x1400d6ba0`

## callees

- `0x140001700`
- `0x140008288`
- `0x140009910`
- `0x140009bf4`
- `0x1400218c0`
- `0x140021a00`
- `0x140021d00`
- `0x14009c16c`
- `0x1400d0258`
- `0x1400d348c`
- `0x1400d42f0`
- `0x1400d5310`
- `0x1400d6d48`
- `0x1400d7f90`
- `0x1400d8584`
- `0x1400d87e0`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x1400d7011`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d7693`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d7011`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d7693`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d75ad`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d75ad`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400d75c8`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400d75c8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d723c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d723c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d7148`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d7148`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d7311`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d73db`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d748c`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d7311`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d73db`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d748c`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400d751e`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400d751e`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d75ea`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d75ea`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7229`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d7229`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d72b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d741f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d74cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d72b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d741f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d74cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d724f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7545`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d724f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d7545`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d71e4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d71e4`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6df5`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7117`
- `ntoskrnl!KeBugCheckEx` at `0x1400d71c1`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7364`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7397`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6df5`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7117`
- `ntoskrnl!KeBugCheckEx` at `0x1400d71c1`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7364`
- `ntoskrnl!KeBugCheckEx` at `0x1400d7397`

## string_xrefs

- `0x1400d70a7`: `Filter read subrequest`

## pseudocode

```c
LONG __fastcall ReadDecrypt(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)
{
  ULONG_PTR v4; // rbx
  ULONG_PTR v5; // rdi
  __int64 v6; // rsi
  int v7; // eax
  __int64 v8; // r12
  __int64 v9; // r13
  char *v10; // r15
  __int64 v11; // rcx
  char *v12; // r14
  char v13; // cl
  unsigned int v14; // edx
  __int64 v15; // r8
  char v16; // dl
  _BOOL8 v17; // rcx
  __int64 v18; // r14
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // edx
  __int64 v24; // rcx
  int v25; // eax
  char v26; // r12
  __int64 v27; // rdx
  int v28; // eax
  int v29; // r14d
  __int64 v30; // rcx
  __int64 v31; // rax
  LONG result; // eax
  KIRQL v33; // al
  unsigned __int64 v34; // rcx
  KIRQL v35; // r15
  unsigned __int64 v36; // rsi
  KIRQL v37; // dl
  KSPIN_LOCK *v38; // rcx
  __int64 v39; // rcx
  __int16 v40; // si
  __int64 v41; // rcx
  __int64 v42; // r8
  __int16 v43; // r15
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int16 v46; // si
  __int64 v47; // rdx
  __int64 v48; // rcx
  KIRQL v49; // al
  KIRQL v50; // r14
  __int64 v51; // rdx
  struct _MDL *v52; // rcx
  __int16 v53; // r8
  __int64 v54; // rax
  int v55; // eax
  int v56; // eax
  _QWORD *v57; // rax
  int v58; // edx
  bool v59; // [rsp+30h] [rbp-D0h]
  bool v60; // [rsp+30h] [rbp-D0h]
  char v61; // [rsp+31h] [rbp-CFh]
  bool v62; // [rsp+32h] [rbp-CEh]
  unsigned int Size; // [rsp+34h] [rbp-CCh]
  char *v65; // [rsp+40h] [rbp-C0h]
  __int64 v67[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v68; // [rsp+150h] [rbp+50h] BYREF
  __int128 v69; // [rsp+160h] [rbp+60h]

  v68 = 0;
  v69 = 0;
  memset(v67, 0, sizeof(v67));
  v4 = *(_QWORD *)(BugCheckParameter2 + 24);
  if ( *(_QWORD *)(v4 + 32) != BugCheckParameter2 && !*(_DWORD *)(BugCheckParameter2 + 32)
    || (v5 = *(_QWORD *)(v4 + 16), v6 = *(_QWORD *)(v5 + 48), BugCheckParameter3 != *(_QWORD *)(v6 + 8))
    || v4 != v5 + 176LL * (*(_BYTE *)(v4 + 136) & 0x3F) + 296 )
  {
    KeBugCheckEx(0x120u, 9u, BugCheckParameter2, BugCheckParameter3, *(_QWORD *)(BugCheckParameter2 + 24));
  }
  v7 = *(_DWORD *)(v6 + 808);
  v62 = (v7 & 0x17F) != 0;
  if ( (*(_BYTE *)(v4 + 136) & 0x40) == 0 )
  {
    v49 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 104));
    v50 = v49;
    if ( *(_DWORD *)(v5 + 120) )
    {
      v42 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
      v43 = *(_WORD *)(v42 + 8);
      if ( (*(_WORD *)(v42 + 10) & 0x20) != 0 && (*(_WORD *)(v42 + 10) & 0x10) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v42 + 24), *(PMDL *)(*(_QWORD *)(v4 + 40) + 8LL));
      v44 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
      *(_QWORD *)v44 = 0;
      *(_DWORD *)(v44 + 8) = 48;
      *(_QWORD *)(v44 + 32) = 0;
      *(_QWORD *)(v44 + 40) = 0;
      *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL) + 8LL) = v43;
      InitializeNextReadSubrequest(v5, v4);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 104), v50);
      *(_BYTE *)(v4 + 144) = (*(_BYTE *)(v4 + 144)
                            ^ (*(_BYTE *)(BugCheckParameter2 + 96)
                             ^ *(_BYTE *)(v4 + 144))
                            & 1)
                           & 0xFD;
      return ReadIssueDirect(v4);
    }
    v37 = v49;
    v38 = (KSPIN_LOCK *)(v5 + 104);
LABEL_69:
    KeReleaseSpinLock(v38, v37);
    return FinishPrimaryRequestIfLastSubrequest(v5);
  }
  v8 = *(unsigned int *)(BugCheckParameter2 + 32);
  v9 = *(_QWORD *)(v4 + 40);
  v10 = (char *)(*(_QWORD *)(v4 + 96) & 0xFFFFFFFFFFFFFFFCuLL);
  v59 = (v7 & 0x40) == 0;
  if ( !(_DWORD)v8 )
  {
    *(_DWORD *)(BugCheckParameter2 + 36) = *(_DWORD *)(v9 + 56);
    if ( v10 )
    {
      v51 = *(_QWORD *)(v9 + 8);
      v52 = *(struct _MDL **)(*(_QWORD *)v5 + 8LL);
      v53 = *(_WORD *)(v51 + 8);
      *(_QWORD *)v51 = 0;
      *(_DWORD *)(v51 + 8) = 48;
      *(_QWORD *)(v51 + 32) = 0;
      *(_QWORD *)(v51 + 40) = 0;
      *(_WORD *)(*(_QWORD *)(v9 + 8) + 8LL) = v53;
      IoBuildPartialMdl(
        v52,
        *(PMDL *)(v9 + 8),
        (char *)v52->StartVa + v52->ByteOffset - *(_QWORD *)(v5 + 64) + *(_QWORD *)v4,
        *(_DWORD *)(v4 + 124));
    }
  }
  v11 = *(_QWORD *)(v9 + 8);
  Size = *(_DWORD *)(BugCheckParameter2 + 36);
  if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
    v12 = *(char **)(v11 + 24);
  else
    v12 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000010u);
  if ( v12 )
  {
    v13 = 0;
  }
  else
  {
    ExAcquireFastMutex((PFAST_MUTEX)(v6 + 2120));
    v12 = (char *)MmMapLockedPagesWithReservedMapping(*(PVOID *)(v6 + 2104), 0x72455646u, *(PMDL *)(v9 + 8), MmCached);
    v13 = 1;
  }
  v14 = Size;
  v61 = v13;
  if ( !(_DWORD)v8 )
  {
    *(_QWORD *)(v4 + 56) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)(v4 + 88) = Size;
    if ( !v13 )
    {
      QueueAdditionalWorkItems(v6, v5, v4, BugCheckParameter2);
      v14 = *(_DWORD *)(BugCheckParameter2 + 36);
      Size = v14;
    }
  }
  v65 = &v12[v8];
  if ( v10 )
    v10 += v8;
  if ( (*(_DWORD *)(v6 + 808) & 0xC000) != 0 && !*(_BYTE *)(v5 + 276) )
  {
    if ( *(char *)(v4 + 136) >= 0 )
    {
      if ( v10 )
        memmove(&v12[v8], v10, v14);
      goto LABEL_56;
    }
LABEL_49:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  v15 = *(_QWORD *)(v5 + 280);
  v16 = *(_BYTE *)(v5 + 276);
  v17 = v15 != -1;
  if ( (v16 != 0) != v17 )
    goto LABEL_49;
  v18 = -1;
  LOBYTE(v17) = v62 && v59;
  v60 = v62 && v59;
  if ( v16 )
    v18 = v8 + v15 + *(_QWORD *)v4 - *(_QWORD *)(v5 + 64);
  if ( v17 )
  {
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v17)
      && (*(_BYTE *)(v6 + 4403) & 8) != 0
      || (v54 = *(_QWORD *)(v6 + 976), *(_WORD *)(v54 + 10) == 1) )
    {
      v20 = 0;
    }
    else
    {
      v20 = *(unsigned int *)(v54 + 28);
      if ( !(_DWORD)v20 )
        v20 = 1;
    }
    LOBYTE(v19) = *(_QWORD *)v4 < v20 * (unsigned __int64)*(unsigned int *)(v6 + 1308);
  }
  else
  {
    v19 = 0;
  }
  InitializeFilterData(v6, v67, v19, v18, *(_QWORD *)(v5 + 288), 0);
  v21 = v8 + *(_QWORD *)(v4 + 8);
  LODWORD(v67[14]) = Size;
  v22 = (__int64)v65;
  if ( v10 )
    v22 = (__int64)v10;
  v67[2] = v21;
  v67[12] = v22;
  v67[11] = (__int64)FveFilteredRead;
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v21) )
    v23 = LODWORD(v67[15]) | 5;
  else
    v23 = 5;
  LODWORD(v67[15]) = v23;
  if ( !v60 || (*(_DWORD *)(v6 + 808) & 0xC000) != 0 || *(char *)(v4 + 136) < 0 )
  {
    if ( !*(_BYTE *)(v5 + 276) )
      goto LABEL_49;
    v23 |= 0x1000u;
    LODWORD(v67[15]) = v23;
  }
  v24 = *(unsigned int *)(BugCheckParameter3 + 884);
  if ( *(_BYTE *)(BugCheckParameter3 + v24 + 1299) || *(_BYTE *)(v6 + v24 + 1955) )
  {
    v55 = *(_DWORD *)(v6 + 4 * v24 + 1748);
    v23 |= 0x800u;
    LODWORD(v67[15]) = v23;
    LODWORD(v67[17]) = v55;
  }
  if ( v10 )
  {
    if ( !*(_DWORD *)(v6 + 4 * v24 + 1712)
      && *(_BYTE *)(v5 + 272)
      && (v56 = MmMdlPageContentsState(*(_QWORD *)(v9 + 8), 2), v23 = v67[15], v56) )
    {
      v26 = 0;
      v67[13] = (__int64)v65;
    }
    else
    {
      v26 = 1;
      v67[13] = (__int64)v10;
    }
  }
  else
  {
    v67[13] = (__int64)v65;
    v25 = MmMdlPageContentsState(*(_QWORD *)(v9 + 8), 2);
    v23 = v67[15];
    if ( !v25 )
    {
      v23 = LODWORD(v67[15]) | 0x40;
      LODWORD(v67[15]) |= 0x40u;
    }
    v26 = 0;
  }
  if ( (*(_DWORD *)(v6 + 808) & 0x100) != 0 )
  {
    v57 = *(_QWORD **)(v6 + 736);
    if ( v57 )
    {
      if ( *v57 )
      {
        v67[9] = *(_QWORD *)(v6 + 736);
        v58 = v23 | 8;
        v67[10] = *(_QWORD *)(v4 + 24);
        LODWORD(v67[15]) = v58;
        if ( (*(_BYTE *)(**(_QWORD **)(v6 + 736) + 48LL) & 1) != 0 )
          LODWORD(v67[15]) = v58 | 0x30;
      }
    }
  }
  FvePerfTraceDevIoCrypto(v6, FVE_PERF_IO_DECRYPT_START, v9, v67[2], v67[14]);
  v27 = *(_QWORD *)(*(_QWORD *)(v4 + 16) + 192LL);
  if ( v27 )
    v28 = FveTestRwParseBlockAndFilter(v67, v27, &v68);
  else
    v28 = FveParseBlockAndFilterEx(v67, &v68);
  v29 = v28;
  FvePerfTraceDevIoCrypto(v6, FVE_PERF_IO_DECRYPT_STOP, v9, v67[2], v67[14]);
  LogFilterTrace((unsigned int)"Filter read subrequest", (unsigned int)&v68, v29, v6, v67[2], v67[14]);
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v30) )
  {
    if ( v29 >= 0 )
    {
      v31 = *(_QWORD *)(v6 + 4736);
      if ( v31 && *(_DWORD *)(v31 + 88) && (HIDWORD(v69) == -1073741662 || DWORD2(v69) == 259) )
        goto LABEL_49;
      goto LABEL_46;
    }
  }
  else if ( v29 >= 0 )
  {
LABEL_46:
    if ( v10 && v26 )
      memmove(v65, v10, Size);
  }
  if ( v67[7] )
    ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v6 + 8) + 9024LL), (PVOID)v67[7]);
  memset(v67, 0, sizeof(v67));
  if ( v29 )
    *(_DWORD *)(v4 + 128) = v29;
LABEL_56:
  result = _InterlockedDecrement((volatile signed __int32 *)(v4 + 132));
  if ( result < 0 )
    KeBugCheckEx(0x120u, 0xBu, v4, 0, result);
  if ( !result )
  {
    *(_QWORD *)(v4 + 64) = MEMORY[0xFFFFF78000000008];
    if ( v61 )
    {
      MmUnmapReservedMapping(*(PVOID *)(v6 + 2104), 0x72455646u, *(PMDL *)(v9 + 8));
      ExReleaseFastMutex((PFAST_MUTEX)(v6 + 2120));
    }
    else
    {
      v39 = *(_QWORD *)(v9 + 8);
      v40 = *(_WORD *)(v39 + 8);
      if ( (*(_BYTE *)(v39 + 10) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v39 + 24), *(PMDL *)(v9 + 8));
      v41 = *(_QWORD *)(v9 + 8);
      *(_QWORD *)v41 = 0;
      *(_DWORD *)(v41 + 8) = 48;
      *(_QWORD *)(v41 + 32) = 0;
      *(_QWORD *)(v41 + 40) = 0;
      *(_WORD *)(*(_QWORD *)(v9 + 8) + 8LL) = v40;
    }
    v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 104));
    v34 = *(_QWORD *)(v5 + 64);
    v35 = v33;
    if ( *(_QWORD *)v4 < v34 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0xFFFFFFFFC0000095uLL);
    v36 = *(_QWORD *)v4 - v34;
    if ( v36 > 0xFFFFFFFF )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0xFFFFFFFFC0000095uLL);
    MergeStatusIntoControl(v5, *(unsigned int *)(v4 + 128), (unsigned int)v36);
    if ( *(int *)(v4 + 128) < 0 && (unsigned int)v36 < *(_DWORD *)(v5 + 124) )
      *(_DWORD *)(v5 + 124) = v36;
    if ( *(_DWORD *)(v5 + 120) && *(int *)(v5 + 128) >= 0 && *(_DWORD *)(v5 + 124) == *(_DWORD *)(v5 + 72) )
    {
      v45 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
      v46 = *(_WORD *)(v45 + 8);
      if ( (*(_WORD *)(v45 + 10) & 0x20) != 0 && (*(_WORD *)(v45 + 10) & 0x10) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v45 + 24), *(PMDL *)(*(_QWORD *)(v4 + 40) + 8LL));
      v47 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
      *(_QWORD *)v47 = 0;
      *(_DWORD *)(v47 + 8) = 48;
      *(_QWORD *)(v47 + 32) = 0;
      *(_QWORD *)(v47 + 40) = 0;
      *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL) + 8LL) = v46;
      InitializeNextReadSubrequest(v5, v4);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 104), v35);
      *(_BYTE *)(v4 + 144) = (*(_BYTE *)(v4 + 144)
                            ^ (*(_BYTE *)(BugCheckParameter2 + 96)
                             ^ *(_BYTE *)(v4 + 144))
                            & 1)
                           & 0xFD;
      v48 = *(_QWORD *)(v4 + 16);
      if ( *(_QWORD *)(v48 + 184) )
        return KeReleaseSemaphore((PRKSEMAPHORE)(v48 + 200), 0, 1, 0);
      return ReadIssueDirect(v4);
    }
    v37 = v35;
    v38 = (KSPIN_LOCK *)(v5 + 104);
    goto LABEL_69;
  }
  return result;
}

```

## disassembly

```asm
0x1400d6d48  mov     [rsp-8+arg_10], rbx
0x1400d6d4d  push    rbp
0x1400d6d4e  push    rsi
0x1400d6d4f  push    rdi
0x1400d6d50  push    r12
0x1400d6d52  push    r13
0x1400d6d54  push    r14
0x1400d6d56  push    r15
0x1400d6d58  lea     rbp, [rsp-80h]
0x1400d6d5d  sub     rsp, 180h
0x1400d6d64  mov     rax, cs:__security_cookie
0x1400d6d6b  xor     rax, rsp
0x1400d6d6e  mov     [rbp+0B0h+var_40], rax
0x1400d6d72  xorps   xmm0, xmm0
0x1400d6d75  mov     [rsp+1B0h+Size+4], rdx
0x1400d6d7a  mov     r14, rdx
0x1400d6d7d  mov     [rsp+1B0h+var_168], rcx
0x1400d6d82  mov     r15, rcx
0x1400d6d85  xor     edx, edx; Val
0x1400d6d87  lea     rcx, [rsp+1B0h+var_160]; void *
0x1400d6d8c  mov     r8d, 100h; Size
0x1400d6d92  movups  [rbp+0B0h+var_60], xmm0
0x1400d6d96  movups  [rbp+0B0h+var_50], xmm0
0x1400d6d9a  call    memset
0x1400d6d9f  mov     rbx, [r14+18h]
0x1400d6da3  xor     r10d, r10d
0x1400d6da6  cmp     [rbx+20h], r14
0x1400d6daa  jnz     loc_1400D752F
0x1400d6db0  mov     rdi, [rbx+10h]
0x1400d6db4  mov     rsi, [rdi+30h]
0x1400d6db8  cmp     r15, [rsi+8]
0x1400d6dbc  jnz     short loc_1400D6DE0
0x1400d6dbe  movzx   edx, byte ptr [rbx+88h]
0x1400d6dc5  mov     eax, edx
0x1400d6dc7  and     eax, 3Fh
0x1400d6dca  imul    rcx, rax, 0B0h
0x1400d6dd1  add     rcx, 128h
0x1400d6dd8  add     rcx, rdi
0x1400d6ddb  cmp     rbx, rcx
0x1400d6dde  jz      short loc_1400D6E02
0x1400d6de0  mov     r9, r15; BugCheckParameter3
0x1400d6de3  mov     [rsp+1B0h+BugCheckParameter4], rbx; BugCheckParameter4
0x1400d6de8  mov     r8, r14; BugCheckParameter2
0x1400d6deb  mov     edx, 9; BugCheckParameter1
0x1400d6df0  mov     ecx, 120h; BugCheckCode
0x1400d6df5  call    cs:__imp_KeBugCheckEx
0x1400d6e02  mov     eax, [rsi+328h]
0x1400d6e08  test    eax, 17Fh
0x1400d6e0d  setnz   [rsp+1B0h+var_17E]
0x1400d6e12  test    dl, 40h
0x1400d6e15  jz      loc_1400D753E
0x1400d6e1b  mov     r15, [rbx+60h]
0x1400d6e1f  test    al, 40h
0x1400d6e21  mov     r12d, [r14+20h]
0x1400d6e25  mov     r13, [rbx+28h]
0x1400d6e29  setz    al
0x1400d6e2c  and     r15, 0FFFFFFFFFFFFFFFCh
0x1400d6e30  mov     [rsp+1B0h+var_180], al
0x1400d6e34  test    r12d, r12d
0x1400d6e37  jnz     short loc_1400D6E4A
0x1400d6e39  mov     eax, [r13+38h]
0x1400d6e3d  mov     [r14+24h], eax
0x1400d6e41  test    r15, r15
0x1400d6e44  jnz     loc_1400D756B
0x1400d6e4a  mov     rcx, [r13+8]; MemoryDescriptorList
0x1400d6e4e  mov     eax, [r14+24h]
0x1400d6e52  mov     dword ptr [rsp+1B0h+Size], eax
0x1400d6e56  test    byte ptr [rcx+0Ah], 5
0x1400d6e5a  jz      loc_1400D71CE
0x1400d6e60  mov     r14, [rcx+18h]
0x1400d6e64  test    r14, r14
0x1400d6e67  jz      loc_1400D75C1
0x1400d6e6d  xor     cl, cl
0x1400d6e6f  mov     edx, dword ptr [rsp+1B0h+Size]
0x1400d6e73  mov     [rsp+1B0h+var_17F], cl
0x1400d6e77  test    r12d, r12d
0x1400d6e7a  jnz     short loc_1400D6EB0
0x1400d6e7c  mov     rax, ds:0FFFFF78000000008h
0x1400d6e86  mov     [rbx+38h], rax
0x1400d6e8a  mov     [rbx+58h], edx
0x1400d6e8d  test    cl, cl
0x1400d6e8f  jnz     short loc_1400D6EB0
0x1400d6e91  mov     r9, [rsp+1B0h+Size+4]
0x1400d6e96  mov     r8, rbx
0x1400d6e99  mov     rdx, rdi
0x1400d6e9c  mov     rcx, rsi
0x1400d6e9f  call    QueueAdditionalWorkItems
0x1400d6ea4  mov     rax, [rsp+1B0h+Size+4]
0x1400d6ea9  mov     edx, [rax+24h]
0x1400d6eac  mov     dword ptr [rsp+1B0h+Size], edx
0x1400d6eb0  lea     rcx, [r12+r14]; void *
0x1400d6eb4  mov     [rsp+1B0h+var_170], rcx
0x1400d6eb9  test    r15, r15
0x1400d6ebc  jnz     loc_1400D7600
0x1400d6ec2  test    dword ptr [rsi+328h], 0C000h
0x1400d6ecc  jnz     loc_1400D72C9
0x1400d6ed2  mov     r8, [rdi+118h]
0x1400d6ed9  xor     ecx, ecx
0x1400d6edb  mov     dl, [rdi+114h]
0x1400d6ee1  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400d6ee5  setnz   cl
0x1400d6ee8  xor     eax, eax
0x1400d6eea  test    dl, dl
0x1400d6eec  setnz   al
0x1400d6eef  cmp     eax, ecx
0x1400d6ef1  jnz     loc_1400D70FF
0x1400d6ef7  mov     cl, [rsp+1B0h+var_180]
0x1400d6efb  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400d6eff  and     cl, [rsp+1B0h+var_17E]
0x1400d6f03  mov     [rsp+1B0h+var_180], cl
0x1400d6f07  test    dl, dl
0x1400d6f09  jnz     loc_1400D7608
0x1400d6f0f  test    cl, cl
0x1400d6f11  jz      loc_1400D71F8
0x1400d6f17  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d6f1c  test    eax, eax
0x1400d6f1e  jz      loc_1400D761A
0x1400d6f24  test    byte ptr [rsi+1133h], 8
0x1400d6f2b  jz      loc_1400D761A
0x1400d6f31  xor     eax, eax
0x1400d6f33  mov     ecx, [rsi+51Ch]
0x1400d6f39  imul    rcx, rax
0x1400d6f3d  cmp     [rbx], rcx
0x1400d6f40  setb    r8b
0x1400d6f44  mov     rax, [rdi+120h]
0x1400d6f4b  lea     rdx, [rsp+1B0h+var_160]
0x1400d6f50  mov     qword ptr [rsp+1B0h+Priority], 0
0x1400d6f59  mov     r9, r14
0x1400d6f5c  mov     rcx, rsi
0x1400d6f5f  mov     [rsp+1B0h+BugCheckParameter4], rax
0x1400d6f64  call    InitializeFilterData
0x1400d6f69  mov     rcx, [rbx+8]
0x1400d6f6d  mov     eax, dword ptr [rsp+1B0h+Size]
0x1400d6f71  add     rcx, r12
0x1400d6f74  mov     r14, [rsp+1B0h+var_170]
0x1400d6f79  test    r15, r15
0x1400d6f7c  mov     [rbp+0B0h+var_F0], eax
0x1400d6f7f  mov     rax, r14
0x1400d6f82  cmovnz  rax, r15
0x1400d6f86  mov     [rsp+1B0h+var_150], rcx
0x1400d6f8b  mov     [rbp+0B0h+var_100], rax
0x1400d6f8f  lea     rax, FveFilteredRead
0x1400d6f96  mov     [rbp+0B0h+var_108], rax
0x1400d6f9a  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d6f9f  test    eax, eax
0x1400d6fa1  jnz     loc_1400D7124
0x1400d6fa7  lea     edx, [rax+5]
0x1400d6faa  cmp     [rsp+1B0h+var_180], 0
0x1400d6faf  mov     [rbp+0B0h+var_E8], edx
0x1400d6fb2  jz      loc_1400D763D
0x1400d6fb8  test    dword ptr [rsi+328h], 0C000h
0x1400d6fc2  jnz     loc_1400D763D
0x1400d6fc8  cmp     byte ptr [rbx+88h], 0
0x1400d6fcf  jl      loc_1400D763D
0x1400d6fd5  mov     rax, [rsp+1B0h+var_168]
0x1400d6fda  mov     ecx, [rax+374h]
0x1400d6fe0  cmp     byte ptr [rax+rcx+513h], 0
0x1400d6fe8  jnz     loc_1400D7656
0x1400d6fee  cmp     byte ptr [rsi+rcx+7A3h], 0
0x1400d6ff6  jnz     loc_1400D7656
0x1400d6ffc  test    r15, r15
0x1400d6fff  jnz     loc_1400D7677
0x1400d7005  mov     [rbp+0B0h+var_F8], r14
0x1400d7009  lea     edx, [r15+2]
0x1400d700d  mov     rcx, [r13+8]
0x1400d7011  call    cs:__imp_MmMdlPageContentsState
0x1400d7018  nop     dword ptr [rax+rax+00h]
0x1400d701d  mov     edx, [rbp+0B0h+var_E8]
0x1400d7020  test    eax, eax
0x1400d7022  jz      loc_1400D766C
0x1400d7028  xor     r12b, r12b
0x1400d702b  test    dword ptr [rsi+328h], 100h
0x1400d7035  jnz     loc_1400D76BE
0x1400d703b  mov     eax, [rbp+0B0h+var_F0]
0x1400d703e  lea     rdx, FVE_PERF_IO_DECRYPT_START
0x1400d7045  mov     r9, [rsp+1B0h+var_150]
0x1400d704a  mov     r8, r13
0x1400d704d  mov     rcx, rsi
0x1400d7050  mov     dword ptr [rsp+1B0h+BugCheckParameter4], eax
0x1400d7054  call    FvePerfTraceDevIoCrypto
0x1400d7059  mov     rax, [rbx+10h]
0x1400d705d  lea     rcx, [rsp+1B0h+var_160]
0x1400d7062  mov     rdx, [rax+0C0h]
0x1400d7069  test    rdx, rdx
0x1400d706c  jnz     loc_1400D7371
0x1400d7072  lea     rdx, [rbp+0B0h+var_60]
0x1400d7076  call    FveParseBlockAndFilterEx
0x1400d707b  mov     r9, [rsp+1B0h+var_150]
0x1400d7080  lea     rdx, FVE_PERF_IO_DECRYPT_STOP
0x1400d7087  mov     r14d, eax
0x1400d708a  mov     r8, r13
0x1400d708d  mov     eax, [rbp+0B0h+var_F0]
0x1400d7090  mov     rcx, rsi
0x1400d7093  mov     dword ptr [rsp+1B0h+BugCheckParameter4], eax
0x1400d7097  call    FvePerfTraceDevIoCrypto
0x1400d709c  mov     eax, [rbp+0B0h+var_F0]
0x1400d709f  lea     rdx, [rbp+0B0h+var_60]
0x1400d70a3  mov     [rsp+1B0h+Priority], eax
0x1400d70a7  lea     rcx, aFilterReadSubr; "Filter read subrequest"
0x1400d70ae  mov     rax, [rsp+1B0h+var_150]
0x1400d70b3  mov     r9, rsi
0x1400d70b6  mov     r8d, r14d
0x1400d70b9  mov     [rsp+1B0h+BugCheckParameter4], rax
0x1400d70be  call    LogFilterTrace
0x1400d70c3  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d70c8  test    eax, eax
0x1400d70ca  jz      short loc_1400D712F
0x1400d70cc  test    r14d, r14d
0x1400d70cf  js      short loc_1400D7134
0x1400d70d1  mov     rax, [rsi+1280h]
0x1400d70d8  test    rax, rax
0x1400d70db  jnz     loc_1400D7709
0x1400d70e1  test    r15, r15
0x1400d70e4  jz      short loc_1400D7134
0x1400d70e6  test    r12b, r12b
0x1400d70e9  jz      short loc_1400D7134
0x1400d70eb  mov     r8d, dword ptr [rsp+1B0h+Size]; Size
0x1400d70f0  mov     rdx, r15; Src
0x1400d70f3  mov     rcx, [rsp+1B0h+var_170]; void *
0x1400d70f8  call    memmove
0x1400d70fd  jmp     short loc_1400D7134
0x1400d70ff  xor     r9d, r9d; BugCheckParameter3
0x1400d7102  mov     [rsp+1B0h+BugCheckParameter4], 0; BugCheckParameter4
0x1400d710b  xor     r8d, r8d; BugCheckParameter2
0x1400d710e  mov     ecx, 120h; BugCheckCode
0x1400d7113  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d7117  call    cs:__imp_KeBugCheckEx
0x1400d7124  mov     edx, [rbp+0B0h+var_E8]
0x1400d7127  or      edx, 5
0x1400d712a  jmp     loc_1400D6FAA
0x1400d712f  test    r14d, r14d
0x1400d7132  jns     short loc_1400D70E1
0x1400d7134  mov     rdx, [rbp+0B0h+Entry]; Entry
0x1400d7138  test    rdx, rdx
0x1400d713b  jz      short loc_1400D7154
0x1400d713d  mov     rcx, [rsi+8]
0x1400d7141  mov     rcx, [rcx+2340h]; Lookaside
0x1400d7148  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d714f  nop     dword ptr [rax+rax+00h]
0x1400d7154  xor     edx, edx; Val
0x1400d7156  lea     rcx, [rsp+1B0h+var_160]; void *
0x1400d715b  mov     r8d, 100h; Size
0x1400d7161  call    memset
0x1400d7166  test    r14d, r14d
0x1400d7169  jnz     loc_1400D7732
0x1400d716f  or      eax, 0FFFFFFFFh
0x1400d7172  lock xadd [rbx+84h], eax
0x1400d717a  sub     eax, 1
0x1400d717d  js      short loc_1400D71AB
0x1400d717f  test    eax, eax
0x1400d7181  jz      short loc_1400D7200
0x1400d7183  mov     rcx, [rbp+0B0h+var_40]
0x1400d7187  xor     rcx, rsp; StackCookie
0x1400d718a  call    __security_check_cookie
0x1400d718f  mov     rbx, [rsp+1B0h+arg_10]
0x1400d7197  add     rsp, 180h
0x1400d719e  pop     r15
0x1400d71a0  pop     r14
0x1400d71a2  pop     r13
0x1400d71a4  pop     r12
0x1400d71a6  pop     rdi
0x1400d71a7  pop     rsi
0x1400d71a8  pop     rbp
0x1400d71a9  retn
0x1400d71ab  xor     r9d, r9d; BugCheckParameter3
0x1400d71ae  cdqe
0x1400d71b0  mov     r8, rbx; BugCheckParameter2
0x1400d71b3  mov     [rsp+1B0h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d71b8  mov     ecx, 120h; BugCheckCode
0x1400d71bd  lea     edx, [r9+0Bh]; BugCheckParameter1
0x1400d71c1  call    cs:__imp_KeBugCheckEx
0x1400d71ce  xor     r9d, r9d; RequestedAddress
0x1400d71d1  mov     [rsp+1B0h+Priority], 40000010h; Priority
0x1400d71d9  xor     edx, edx; AccessMode
0x1400d71db  mov     dword ptr [rsp+1B0h+BugCheckParameter4], r10d; BugCheckOnFailure
0x1400d71e0  lea     r8d, [r9+1]; CacheType
0x1400d71e4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d71eb  nop     dword ptr [rax+rax+00h]
0x1400d71f0  mov     r14, rax
0x1400d71f3  jmp     loc_1400D6E64
0x1400d71f8  xor     r8d, r8d
0x1400d71fb  jmp     loc_1400D6F44
0x1400d7200  cmp     [rsp+1B0h+var_17F], 0
0x1400d7205  mov     rax, ds:0FFFFF78000000008h
0x1400d720f  mov     [rbx+40h], rax
0x1400d7213  jz      loc_1400D72FC
0x1400d7219  mov     r8, [r13+8]; MemoryDescriptorList
0x1400d721d  mov     edx, 72455646h; PoolTag
0x1400d7222  mov     rcx, [rsi+838h]; BaseAddress
0x1400d7229  call    cs:__imp_MmUnmapReservedMapping
0x1400d7230  nop     dword ptr [rax+rax+00h]
0x1400d7235  lea     rcx, [rsi+848h]; FastMutex
0x1400d723c  call    cs:__imp_ExReleaseFastMutex
0x1400d7243  nop     dword ptr [rax+rax+00h]
0x1400d7248  lea     r14, [rdi+68h]
0x1400d724c  mov     rcx, r14; SpinLock
0x1400d724f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d7256  nop     dword ptr [rax+rax+00h]
0x1400d725b  mov     rcx, [rdi+40h]
0x1400d725f  mov     r15b, al
  ... truncated ...
```
