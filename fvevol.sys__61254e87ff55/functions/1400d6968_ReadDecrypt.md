# ReadDecrypt

- ea: `0x1400d6968`
- end: `0x1400d7367`
- name: `ReadDecrypt`
- size: `2559`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x1400d67c0`

## callees

- `0x140001710`
- `0x140008348`
- `0x1400099d0`
- `0x140009cb4`
- `0x140022bf0`
- `0x140022d40`
- `0x140023040`
- `0x14009e16c`
- `0x1400d34a4`
- `0x1400d55d0`
- `0x1400d6968`
- `0x1400d7b80`
- `0x1400d8170`
- `0x1400d83c0`
- `0x1400d87d0`
- `0x1400d95c0`
- `0x1400da17c`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x1400d6c33`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d728d`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d6c33`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400d728d`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d71a7`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d71a7`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400d71c2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400d71c2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d6e5e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400d6e5e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d6d6a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d6d6a`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d6f33`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d6ffd`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d70ae`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d6f33`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d6ffd`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d70ae`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d71e4`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400d71e4`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d6e4b`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400d6e4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d6ed2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7041`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d70f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d6ed2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d7041`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d70f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d6e71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d713f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d6e71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d713f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d6e06`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d6e06`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6a15`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6d39`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6de3`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6f86`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6fb9`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6a15`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6d39`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6de3`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6f86`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6fb9`

## string_xrefs

- `0x1400d6cc9`: `Filter read subrequest`

## pseudocode

```c
__int64 __fastcall ReadDecrypt(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)
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
  __int64 v14; // rdx
  __int64 v15; // r8
  _BOOL8 v16; // rcx
  __int64 v17; // r14
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // edx
  __int64 v24; // rcx
  int v25; // eax
  char v26; // r12
  __int64 v27; // rdx
  int v28; // eax
  int v29; // r14d
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 result; // rax
  KIRQL v34; // al
  unsigned __int64 v35; // rcx
  KIRQL v36; // r15
  unsigned __int64 v37; // rsi
  KIRQL v38; // dl
  KSPIN_LOCK *v39; // rcx
  __int64 v40; // rcx
  __int16 v41; // si
  __int64 v42; // rcx
  __int64 v43; // r8
  __int16 v44; // r15
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int16 v47; // si
  __int64 v48; // rdx
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
    || v4 != v5 + 192LL * (*(_BYTE *)(v4 + 136) & 0x3F) + 312 )
  {
    KeBugCheckEx(0x120u, 9u, BugCheckParameter2, BugCheckParameter3, *(_QWORD *)(BugCheckParameter2 + 24));
  }
  v7 = *(_DWORD *)(v6 + 808);
  v59 = (v7 & 0x17F) != 0;
  if ( (*(_BYTE *)(v4 + 136) & 0x40) != 0 )
  {
    v8 = *(unsigned int *)(BugCheckParameter2 + 32);
    v9 = *(_QWORD *)(v4 + 40);
    v62 = (v7 & 0x40) == 0;
    v10 = (char *)(*(_QWORD *)(v4 + 96) & 0xFFFFFFFFFFFFFFFCuLL);
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
        v14 = *(unsigned int *)(BugCheckParameter2 + 36);
        Size = *(_DWORD *)(BugCheckParameter2 + 36);
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
          memmove(&v12[v8], v10, (unsigned int)v14);
LABEL_56:
        result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v4 + 132));
        if ( (int)result < 0 )
          KeBugCheckEx(0x120u, 0xBu, v4, 0, (int)result);
        if ( (_DWORD)result )
          return result;
        *(_QWORD *)(v4 + 64) = MEMORY[0xFFFFF78000000008];
        if ( v61 )
        {
          MmUnmapReservedMapping(*(PVOID *)(v6 + 2104), 0x72455646u, *(PMDL *)(v9 + 8));
          ExReleaseFastMutex((PFAST_MUTEX)(v6 + 2120));
        }
        else
        {
          v40 = *(_QWORD *)(v9 + 8);
          v41 = *(_WORD *)(v40 + 8);
          if ( (*(_BYTE *)(v40 + 10) & 0x20) != 0 )
            MmUnmapLockedPages(*(PVOID *)(v40 + 24), *(PMDL *)(v9 + 8));
          v42 = *(_QWORD *)(v9 + 8);
          *(_QWORD *)v42 = 0;
          *(_DWORD *)(v42 + 8) = 48;
          *(_QWORD *)(v42 + 32) = 0;
          *(_QWORD *)(v42 + 40) = 0;
          *(_WORD *)(*(_QWORD *)(v9 + 8) + 8LL) = v41;
        }
        v34 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 104));
        v35 = *(_QWORD *)(v5 + 64);
        v36 = v34;
        if ( *(_QWORD *)v4 < v35 )
          KeBugCheckEx(0x120u, 0xCu, 0, 0, 0xFFFFFFFFC0000095uLL);
        v37 = *(_QWORD *)v4 - v35;
        if ( v37 > 0xFFFFFFFF )
          KeBugCheckEx(0x120u, 0xCu, 0, 0, 0xFFFFFFFFC0000095uLL);
        MergeStatusIntoControl(v5, *(unsigned int *)(v4 + 128), (unsigned int)v37);
        if ( *(int *)(v4 + 128) < 0 && (unsigned int)v37 < *(_DWORD *)(v5 + 124) )
          *(_DWORD *)(v5 + 124) = v37;
        if ( *(_DWORD *)(v5 + 120) && *(int *)(v5 + 128) >= 0 && *(_DWORD *)(v5 + 124) == *(_DWORD *)(v5 + 72) )
        {
          v46 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
          v47 = *(_WORD *)(v46 + 8);
          if ( (*(_WORD *)(v46 + 10) & 0x20) != 0 && (*(_WORD *)(v46 + 10) & 0x10) != 0 )
            MmUnmapLockedPages(*(PVOID *)(v46 + 24), *(PMDL *)(*(_QWORD *)(v4 + 40) + 8LL));
          v48 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
          *(_QWORD *)v48 = 0;
          *(_DWORD *)(v48 + 8) = 48;
          *(_QWORD *)(v48 + 32) = 0;
          *(_QWORD *)(v48 + 40) = 0;
          *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL) + 8LL) = v47;
          InitializeNextReadSubrequest(v5, v4);
          KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 104), v36);
          *(_BYTE *)(v4 + 144) = (*(_BYTE *)(v4 + 144)
                                ^ (*(_BYTE *)(BugCheckParameter2 + 96)
                                 ^ *(_BYTE *)(v4 + 144))
                                & 1)
                               & 0xFD;
          return ReadIssue(v4);
        }
        v38 = v36;
        v39 = (KSPIN_LOCK *)(v5 + 104);
LABEL_69:
        KeReleaseSpinLock(v39, v38);
        return FinishPrimaryRequestIfLastSubrequest(v5);
      }
LABEL_49:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
    }
    v15 = *(_QWORD *)(v5 + 280);
    LOBYTE(v14) = *(_BYTE *)(v5 + 276);
    v16 = v15 != -1;
    if ( ((_BYTE)v14 != 0) != v16 )
      goto LABEL_49;
    v17 = -1;
    LOBYTE(v16) = v62 && v59;
    v60 = v62 && v59;
    if ( (_BYTE)v14 )
      v17 = v8 + v15 + *(_QWORD *)v4 - *(_QWORD *)(v5 + 64);
    if ( v16 )
    {
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v16, v14)
        && (*(_BYTE *)(v6 + 4419) & 8) != 0
        || (v54 = *(_QWORD *)(v6 + 976), *(_WORD *)(v54 + 10) == 1) )
      {
        v19 = 0;
      }
      else
      {
        v19 = *(unsigned int *)(v54 + 28);
        if ( !(_DWORD)v19 )
          v19 = 1;
      }
      LOBYTE(v18) = *(_QWORD *)v4 < v19 * (unsigned __int64)*(unsigned int *)(v6 + 1308);
    }
    else
    {
      v18 = 0;
    }
    InitializeFilterData(v6, v67, v18, v17, *(_QWORD *)(v5 + 288), 0);
    v21 = v8 + *(_QWORD *)(v4 + 8);
    LODWORD(v67[14]) = Size;
    v22 = (__int64)v65;
    if ( v10 )
      v22 = (__int64)v10;
    v67[2] = v21;
    v67[12] = v22;
    v67[11] = (__int64)FveFilteredRead;
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v21, v20) )
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
    if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v31, v30) )
    {
      if ( v29 >= 0 )
      {
        v32 = *(_QWORD *)(v6 + 4752);
        if ( v32 && *(_DWORD *)(v32 + 88) && (HIDWORD(v69) == -1073741662 || DWORD2(v69) == 259) )
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
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(v6 + 8) + 9272LL), (PVOID)v67[7]);
    memset(v67, 0, sizeof(v67));
    if ( v29 )
      *(_DWORD *)(v4 + 128) = v29;
    goto LABEL_56;
  }
  v49 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 104));
  v50 = v49;
  if ( !*(_DWORD *)(v5 + 120) )
  {
    v38 = v49;
    v39 = (KSPIN_LOCK *)(v5 + 104);
    goto LABEL_69;
  }
  v43 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
  v44 = *(_WORD *)(v43 + 8);
  if ( (*(_WORD *)(v43 + 10) & 0x20) != 0 && (*(_WORD *)(v43 + 10) & 0x10) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v43 + 24), *(PMDL *)(*(_QWORD *)(v4 + 40) + 8LL));
  v45 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL);
  *(_QWORD *)v45 = 0;
  *(_DWORD *)(v45 + 8) = 48;
  *(_QWORD *)(v45 + 32) = 0;
  *(_QWORD *)(v45 + 40) = 0;
  *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 8LL) + 8LL) = v44;
  InitializeNextReadSubrequest(v5, v4);
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 104), v50);
  *(_BYTE *)(v4 + 144) = (*(_BYTE *)(v4 + 144)
                        ^ (*(_BYTE *)(BugCheckParameter2 + 96)
                         ^ *(_BYTE *)(v4 + 144))
                        & 1)
                       & 0xFD;
  return ReadIssueDirect(v4);
}

```

## disassembly

```asm
0x1400d6968  mov     [rsp-8+arg_10], rbx
0x1400d696d  push    rbp
0x1400d696e  push    rsi
0x1400d696f  push    rdi
0x1400d6970  push    r12
0x1400d6972  push    r13
0x1400d6974  push    r14
0x1400d6976  push    r15
0x1400d6978  lea     rbp, [rsp-80h]
0x1400d697d  sub     rsp, 180h
0x1400d6984  mov     rax, cs:__security_cookie
0x1400d698b  xor     rax, rsp
0x1400d698e  mov     [rbp+0B0h+var_40], rax
0x1400d6992  xorps   xmm0, xmm0
0x1400d6995  mov     [rsp+1B0h+Size+4], rdx
0x1400d699a  mov     r14, rdx
0x1400d699d  mov     [rsp+1B0h+var_168], rcx
0x1400d69a2  mov     r15, rcx
0x1400d69a5  xor     edx, edx; Val
0x1400d69a7  lea     rcx, [rsp+1B0h+var_160]; void *
0x1400d69ac  mov     r8d, 100h; Size
0x1400d69b2  movups  [rbp+0B0h+var_60], xmm0
0x1400d69b6  movups  [rbp+0B0h+var_50], xmm0
0x1400d69ba  call    memset
0x1400d69bf  mov     rbx, [r14+18h]
0x1400d69c3  xor     r10d, r10d
0x1400d69c6  cmp     [rbx+20h], r14
0x1400d69ca  jnz     loc_1400D7129
0x1400d69d0  mov     rdi, [rbx+10h]
0x1400d69d4  mov     rsi, [rdi+30h]
0x1400d69d8  cmp     r15, [rsi+8]
0x1400d69dc  jnz     short loc_1400D6A00
0x1400d69de  movzx   ecx, byte ptr [rbx+88h]
0x1400d69e5  mov     eax, ecx
0x1400d69e7  and     eax, 3Fh
0x1400d69ea  lea     rax, [rax+rax*2]
0x1400d69ee  shl     rax, 6
0x1400d69f2  add     rax, 138h
0x1400d69f8  add     rax, rdi
0x1400d69fb  cmp     rbx, rax
0x1400d69fe  jz      short loc_1400D6A22
0x1400d6a00  mov     r9, r15; BugCheckParameter3
0x1400d6a03  mov     [rsp+1B0h+BugCheckParameter4], rbx; BugCheckParameter4
0x1400d6a08  mov     r8, r14; BugCheckParameter2
0x1400d6a0b  mov     edx, 9; BugCheckParameter1
0x1400d6a10  mov     ecx, 120h; BugCheckCode
0x1400d6a15  call    cs:__imp_KeBugCheckEx
0x1400d6a22  mov     eax, [rsi+328h]
0x1400d6a28  test    eax, 17Fh
0x1400d6a2d  setnz   r8b
0x1400d6a31  mov     [rsp+1B0h+var_180], r8b
0x1400d6a36  test    cl, 40h
0x1400d6a39  jz      loc_1400D7138
0x1400d6a3f  mov     r15, [rbx+60h]
0x1400d6a43  test    al, 40h
0x1400d6a45  mov     r12d, [r14+20h]
0x1400d6a49  mov     r13, [rbx+28h]
0x1400d6a4d  setz    [rsp+1B0h+var_17E]
0x1400d6a52  and     r15, 0FFFFFFFFFFFFFFFCh
0x1400d6a56  test    r12d, r12d
0x1400d6a59  jnz     short loc_1400D6A6C
0x1400d6a5b  mov     eax, [r13+38h]
0x1400d6a5f  mov     [r14+24h], eax
0x1400d6a63  test    r15, r15
0x1400d6a66  jnz     loc_1400D7165
0x1400d6a6c  mov     rcx, [r13+8]; MemoryDescriptorList
0x1400d6a70  mov     eax, [r14+24h]
0x1400d6a74  mov     dword ptr [rsp+1B0h+Size], eax
0x1400d6a78  test    byte ptr [rcx+0Ah], 5
0x1400d6a7c  jz      loc_1400D6DF0
0x1400d6a82  mov     r14, [rcx+18h]
0x1400d6a86  test    r14, r14
0x1400d6a89  jz      loc_1400D71BB
0x1400d6a8f  xor     cl, cl
0x1400d6a91  mov     edx, dword ptr [rsp+1B0h+Size]
0x1400d6a95  mov     [rsp+1B0h+var_17F], cl
0x1400d6a99  test    r12d, r12d
0x1400d6a9c  jnz     short loc_1400D6AD2
0x1400d6a9e  mov     rax, ds:0FFFFF78000000008h
0x1400d6aa8  mov     [rbx+38h], rax
0x1400d6aac  mov     [rbx+58h], edx
0x1400d6aaf  test    cl, cl
0x1400d6ab1  jnz     short loc_1400D6AD2
0x1400d6ab3  mov     r9, [rsp+1B0h+Size+4]
0x1400d6ab8  mov     r8, rbx
0x1400d6abb  mov     rdx, rdi
0x1400d6abe  mov     rcx, rsi
0x1400d6ac1  call    QueueAdditionalWorkItems
0x1400d6ac6  mov     rax, [rsp+1B0h+Size+4]
0x1400d6acb  mov     edx, [rax+24h]
0x1400d6ace  mov     dword ptr [rsp+1B0h+Size], edx
0x1400d6ad2  lea     rcx, [r12+r14]; void *
0x1400d6ad6  mov     [rsp+1B0h+var_170], rcx
0x1400d6adb  test    r15, r15
0x1400d6ade  jnz     loc_1400D71FA
0x1400d6ae4  test    dword ptr [rsi+328h], 0C000h
0x1400d6aee  jnz     loc_1400D6EEB
0x1400d6af4  mov     r8, [rdi+118h]
0x1400d6afb  xor     ecx, ecx
0x1400d6afd  mov     dl, [rdi+114h]
0x1400d6b03  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400d6b07  setnz   cl
0x1400d6b0a  xor     eax, eax
0x1400d6b0c  test    dl, dl
0x1400d6b0e  setnz   al
0x1400d6b11  cmp     eax, ecx
0x1400d6b13  jnz     loc_1400D6D21
0x1400d6b19  mov     cl, [rsp+1B0h+var_180]
0x1400d6b1d  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400d6b21  and     cl, [rsp+1B0h+var_17E]
0x1400d6b25  mov     [rsp+1B0h+var_180], cl
0x1400d6b29  test    dl, dl
0x1400d6b2b  jnz     loc_1400D7202
0x1400d6b31  test    cl, cl
0x1400d6b33  jz      loc_1400D6E1A
0x1400d6b39  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d6b3e  test    eax, eax
0x1400d6b40  jz      loc_1400D7214
0x1400d6b46  test    byte ptr [rsi+1143h], 8
0x1400d6b4d  jz      loc_1400D7214
0x1400d6b53  xor     eax, eax
0x1400d6b55  mov     ecx, [rsi+51Ch]
0x1400d6b5b  imul    rcx, rax
0x1400d6b5f  cmp     [rbx], rcx
0x1400d6b62  setb    r8b
0x1400d6b66  mov     rax, [rdi+120h]
0x1400d6b6d  lea     rdx, [rsp+1B0h+var_160]
0x1400d6b72  mov     qword ptr [rsp+1B0h+Priority], 0
0x1400d6b7b  mov     r9, r14
0x1400d6b7e  mov     rcx, rsi
0x1400d6b81  mov     [rsp+1B0h+BugCheckParameter4], rax
0x1400d6b86  call    InitializeFilterData
0x1400d6b8b  mov     rcx, [rbx+8]
0x1400d6b8f  mov     eax, dword ptr [rsp+1B0h+Size]
0x1400d6b93  add     rcx, r12
0x1400d6b96  mov     r14, [rsp+1B0h+var_170]
0x1400d6b9b  test    r15, r15
0x1400d6b9e  mov     [rbp+0B0h+var_F0], eax
0x1400d6ba1  mov     rax, r14
0x1400d6ba4  cmovnz  rax, r15
0x1400d6ba8  mov     [rsp+1B0h+var_150], rcx
0x1400d6bad  mov     [rbp+0B0h+var_100], rax
0x1400d6bb1  lea     rax, FveFilteredRead
0x1400d6bb8  mov     [rbp+0B0h+var_108], rax
0x1400d6bbc  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d6bc1  test    eax, eax
0x1400d6bc3  jnz     loc_1400D6D46
0x1400d6bc9  lea     edx, [rax+5]
0x1400d6bcc  cmp     [rsp+1B0h+var_180], 0
0x1400d6bd1  mov     [rbp+0B0h+var_E8], edx
0x1400d6bd4  jz      loc_1400D7237
0x1400d6bda  test    dword ptr [rsi+328h], 0C000h
0x1400d6be4  jnz     loc_1400D7237
0x1400d6bea  cmp     byte ptr [rbx+88h], 0
0x1400d6bf1  jl      loc_1400D7237
0x1400d6bf7  mov     rax, [rsp+1B0h+var_168]
0x1400d6bfc  mov     ecx, [rax+374h]
0x1400d6c02  cmp     byte ptr [rax+rcx+513h], 0
0x1400d6c0a  jnz     loc_1400D7250
0x1400d6c10  cmp     byte ptr [rsi+rcx+7A3h], 0
0x1400d6c18  jnz     loc_1400D7250
0x1400d6c1e  test    r15, r15
0x1400d6c21  jnz     loc_1400D7271
0x1400d6c27  mov     [rbp+0B0h+var_F8], r14
0x1400d6c2b  lea     edx, [r15+2]
0x1400d6c2f  mov     rcx, [r13+8]
0x1400d6c33  call    cs:__imp_MmMdlPageContentsState
0x1400d6c3a  nop     dword ptr [rax+rax+00h]
0x1400d6c3f  mov     edx, [rbp+0B0h+var_E8]
0x1400d6c42  test    eax, eax
0x1400d6c44  jz      loc_1400D7266
0x1400d6c4a  xor     r12b, r12b
0x1400d6c4d  test    dword ptr [rsi+328h], 100h
0x1400d6c57  jnz     loc_1400D72B8
0x1400d6c5d  mov     eax, [rbp+0B0h+var_F0]
0x1400d6c60  lea     rdx, FVE_PERF_IO_DECRYPT_START
0x1400d6c67  mov     r9, [rsp+1B0h+var_150]
0x1400d6c6c  mov     r8, r13
0x1400d6c6f  mov     rcx, rsi
0x1400d6c72  mov     dword ptr [rsp+1B0h+BugCheckParameter4], eax
0x1400d6c76  call    FvePerfTraceDevIoCrypto
0x1400d6c7b  mov     rax, [rbx+10h]
0x1400d6c7f  lea     rcx, [rsp+1B0h+var_160]
0x1400d6c84  mov     rdx, [rax+0C0h]
0x1400d6c8b  test    rdx, rdx
0x1400d6c8e  jnz     loc_1400D6F93
0x1400d6c94  lea     rdx, [rbp+0B0h+var_60]
0x1400d6c98  call    FveParseBlockAndFilterEx
0x1400d6c9d  mov     r9, [rsp+1B0h+var_150]
0x1400d6ca2  lea     rdx, FVE_PERF_IO_DECRYPT_STOP
0x1400d6ca9  mov     r14d, eax
0x1400d6cac  mov     r8, r13
0x1400d6caf  mov     eax, [rbp+0B0h+var_F0]
0x1400d6cb2  mov     rcx, rsi
0x1400d6cb5  mov     dword ptr [rsp+1B0h+BugCheckParameter4], eax
0x1400d6cb9  call    FvePerfTraceDevIoCrypto
0x1400d6cbe  mov     eax, [rbp+0B0h+var_F0]
0x1400d6cc1  lea     rdx, [rbp+0B0h+var_60]
0x1400d6cc5  mov     [rsp+1B0h+Priority], eax
0x1400d6cc9  lea     rcx, aFilterReadSubr; "Filter read subrequest"
0x1400d6cd0  mov     rax, [rsp+1B0h+var_150]
0x1400d6cd5  mov     r9, rsi
0x1400d6cd8  mov     r8d, r14d
0x1400d6cdb  mov     [rsp+1B0h+BugCheckParameter4], rax
0x1400d6ce0  call    LogFilterTrace
0x1400d6ce5  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400d6cea  test    eax, eax
0x1400d6cec  jz      short loc_1400D6D51
0x1400d6cee  test    r14d, r14d
0x1400d6cf1  js      short loc_1400D6D56
0x1400d6cf3  mov     rax, [rsi+1290h]
0x1400d6cfa  test    rax, rax
0x1400d6cfd  jnz     loc_1400D7303
0x1400d6d03  test    r15, r15
0x1400d6d06  jz      short loc_1400D6D56
0x1400d6d08  test    r12b, r12b
0x1400d6d0b  jz      short loc_1400D6D56
0x1400d6d0d  mov     r8d, dword ptr [rsp+1B0h+Size]; Size
0x1400d6d12  mov     rdx, r15; Src
0x1400d6d15  mov     rcx, [rsp+1B0h+var_170]; void *
0x1400d6d1a  call    memmove
0x1400d6d1f  jmp     short loc_1400D6D56
0x1400d6d21  xor     r9d, r9d; BugCheckParameter3
0x1400d6d24  mov     [rsp+1B0h+BugCheckParameter4], 0; BugCheckParameter4
0x1400d6d2d  xor     r8d, r8d; BugCheckParameter2
0x1400d6d30  mov     ecx, 120h; BugCheckCode
0x1400d6d35  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d6d39  call    cs:__imp_KeBugCheckEx
0x1400d6d46  mov     edx, [rbp+0B0h+var_E8]
0x1400d6d49  or      edx, 5
0x1400d6d4c  jmp     loc_1400D6BCC
0x1400d6d51  test    r14d, r14d
0x1400d6d54  jns     short loc_1400D6D03
0x1400d6d56  mov     rdx, [rbp+0B0h+Entry]; Entry
0x1400d6d5a  test    rdx, rdx
0x1400d6d5d  jz      short loc_1400D6D76
0x1400d6d5f  mov     rcx, [rsi+8]
0x1400d6d63  mov     rcx, [rcx+2438h]; Lookaside
0x1400d6d6a  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d6d71  nop     dword ptr [rax+rax+00h]
0x1400d6d76  xor     edx, edx; Val
0x1400d6d78  lea     rcx, [rsp+1B0h+var_160]; void *
0x1400d6d7d  mov     r8d, 100h; Size
0x1400d6d83  call    memset
0x1400d6d88  test    r14d, r14d
0x1400d6d8b  jnz     loc_1400D732C
0x1400d6d91  or      eax, 0FFFFFFFFh
0x1400d6d94  lock xadd [rbx+84h], eax
0x1400d6d9c  sub     eax, 1
0x1400d6d9f  js      short loc_1400D6DCD
0x1400d6da1  test    eax, eax
0x1400d6da3  jz      short loc_1400D6E22
0x1400d6da5  mov     rcx, [rbp+0B0h+var_40]
0x1400d6da9  xor     rcx, rsp; StackCookie
0x1400d6dac  call    __security_check_cookie
0x1400d6db1  mov     rbx, [rsp+1B0h+arg_10]
0x1400d6db9  add     rsp, 180h
0x1400d6dc0  pop     r15
0x1400d6dc2  pop     r14
0x1400d6dc4  pop     r13
0x1400d6dc6  pop     r12
0x1400d6dc8  pop     rdi
0x1400d6dc9  pop     rsi
0x1400d6dca  pop     rbp
0x1400d6dcb  retn
0x1400d6dcd  xor     r9d, r9d; BugCheckParameter3
0x1400d6dd0  cdqe
0x1400d6dd2  mov     r8, rbx; BugCheckParameter2
0x1400d6dd5  mov     [rsp+1B0h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d6dda  mov     ecx, 120h; BugCheckCode
0x1400d6ddf  lea     edx, [r9+0Bh]; BugCheckParameter1
0x1400d6de3  call    cs:__imp_KeBugCheckEx
0x1400d6df0  xor     r9d, r9d; RequestedAddress
0x1400d6df3  mov     [rsp+1B0h+Priority], 40000010h; Priority
0x1400d6dfb  xor     edx, edx; AccessMode
0x1400d6dfd  mov     dword ptr [rsp+1B0h+BugCheckParameter4], r10d; BugCheckOnFailure
0x1400d6e02  lea     r8d, [r9+1]; CacheType
0x1400d6e06  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d6e0d  nop     dword ptr [rax+rax+00h]
0x1400d6e12  mov     r14, rax
0x1400d6e15  jmp     loc_1400D6A86
0x1400d6e1a  xor     r8d, r8d
0x1400d6e1d  jmp     loc_1400D6B66
0x1400d6e22  cmp     [rsp+1B0h+var_17F], 0
0x1400d6e27  mov     rax, ds:0FFFFF78000000008h
0x1400d6e31  mov     [rbx+40h], rax
0x1400d6e35  jz      loc_1400D6F1E
0x1400d6e3b  mov     r8, [r13+8]; MemoryDescriptorList
0x1400d6e3f  mov     edx, 72455646h; PoolTag
0x1400d6e44  mov     rcx, [rsi+838h]; BaseAddress
0x1400d6e4b  call    cs:__imp_MmUnmapReservedMapping
0x1400d6e52  nop     dword ptr [rax+rax+00h]
0x1400d6e57  lea     rcx, [rsi+848h]; FastMutex
0x1400d6e5e  call    cs:__imp_ExReleaseFastMutex
0x1400d6e65  nop     dword ptr [rax+rax+00h]
0x1400d6e6a  lea     r14, [rdi+68h]
0x1400d6e6e  mov     rcx, r14; SpinLock
0x1400d6e71  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d6e78  nop     dword ptr [rax+rax+00h]
0x1400d6e7d  mov     rcx, [rdi+40h]
  ... truncated ...
```
