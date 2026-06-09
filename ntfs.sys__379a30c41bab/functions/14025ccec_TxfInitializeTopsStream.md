# TxfInitializeTopsStream

- ea: `0x14025ccec`
- end: `0x14025e6e6`
- name: `TxfInitializeTopsStream`
- size: `6650`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14025a318`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000ea70`
- `0x140012e70`
- `0x140021590`
- `0x1400410a8`
- `0x140049d00`
- `0x140054298`
- `0x1400592c0`
- `0x140059740`
- `0x140059c60`
- `0x1400e3390`
- `0x140125100`
- `0x140125fc0`
- `0x140126220`
- `0x140128da0`
- `0x14013c320`
- `0x1401403d0`
- `0x140143730`
- `0x140145ddc`
- `0x140150c10`
- `0x140150cd0`
- `0x140158130`
- `0x1401597b8`
- `0x140160c30`
- `0x140162110`
- `0x140163fc8`
- `0x140165c60`
- `0x140191424`
- `0x140196e80`
- `0x1401e06b0`
- `0x1401fd870`
- `0x14025ccec`
- `0x14025e6ec`

## import_xrefs

- `ntoskrnl!CcZeroData` at `0x14025e34a`
- `ntoskrnl!CcZeroData` at `0x14025e34a`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14025e18a`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14025e18a`
- `ntoskrnl!KeReleaseMutex` at `0x14025d9fe`
- `ntoskrnl!KeReleaseMutex` at `0x14025d9fe`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14025e440`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14025e440`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14025e384`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14025e384`
- `ntoskrnl!DbgPrintEx` at `0x14025d37d`
- `ntoskrnl!DbgPrintEx` at `0x14025d37d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14025d9d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14025d9d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e052`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e084`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e11a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e052`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e084`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e11a`
- `ntoskrnl!CcUnpinData` at `0x14025d980`
- `ntoskrnl!CcUnpinData` at `0x14025db3c`
- `ntoskrnl!CcUnpinData` at `0x14025e629`
- `ntoskrnl!CcUnpinData` at `0x1402b98cc`
- `ntoskrnl!CcUnpinData` at `0x14025d980`
- `ntoskrnl!CcUnpinData` at `0x14025db3c`
- `ntoskrnl!CcUnpinData` at `0x14025e629`
- `ntoskrnl!CcUnpinData` at `0x1402b98cc`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025da2a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025da2a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025da50`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025da50`
- `ntoskrnl!RtlCompareMemory` at `0x14025d8f9`
- `ntoskrnl!RtlCompareMemory` at `0x14025d8f9`
- `ntoskrnl!ExRaiseStatus` at `0x14025cdde`
- `ntoskrnl!ExRaiseStatus` at `0x14025cdde`
- `ntoskrnl!CcFlushCache` at `0x14025e471`
- `ntoskrnl!CcFlushCache` at `0x14025e471`

## string_xrefs

- `0x14025e67b`: `compressed`

## pseudocode

```c
void __fastcall TxfInitializeTopsStream(_DWORD *a1, __int64 a2, char a3)
{
  char v3; // si
  __int64 v6; // r15
  char v7; // r12
  __int64 v8; // r13
  __int64 v9; // r13
  unsigned int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // r8
  __int64 i; // rcx
  int v16; // eax
  __int64 v17; // rcx
  char v18; // al
  char v19; // al
  __int16 v20; // dx
  _QWORD *v21; // r9
  __int16 v22; // ax
  int v23; // ecx
  int v24; // r13d
  __int64 v25; // r12
  unsigned int Attribute; // eax
  int v27; // ecx
  unsigned int v28; // edi
  __int64 v29; // rdi
  int v30; // r9d
  _WORD *v31; // rcx
  char *v32; // rdx
  int v33; // ecx
  _QWORD *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdi
  void *v37; // rcx
  unsigned int v38; // eax
  int v39; // ecx
  unsigned int v40; // edi
  __int64 v41; // rsi
  int v42; // r9d
  signed __int64 *v43; // r13
  __int64 v44; // rdi
  size_t QuadPart; // rdi
  PVOID PoolWithTag; // rax
  _DWORD *v47; // rax
  void *v48; // rdx
  size_t v49; // r8
  PVOID v50; // rax
  int v51; // eax
  __int64 v52; // rdi
  int v53; // r9d
  int v54; // edx
  signed __int64 v55; // rcx
  signed __int64 v56; // rax
  int v57; // edx
  signed __int64 v58; // r8
  signed __int64 v59; // rdi
  __int64 v60; // rcx
  __int64 v61; // r8
  union _LARGE_INTEGER v62; // rax
  union _LARGE_INTEGER v63; // rdi
  unsigned __int64 v64; // rdi
  int v65; // edx
  signed __int64 v66; // rcx
  signed __int64 v67; // r8
  unsigned __int64 v68; // rax
  int v69; // r9d
  __int64 j; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  const char *v73; // rcx
  PLARGE_INTEGER Timeout; // [rsp+88h] [rbp-228h]
  int Timeouta; // [rsp+88h] [rbp-228h]
  int v76; // [rsp+98h] [rbp-218h]
  int v77; // [rsp+98h] [rbp-218h]
  int v78; // [rsp+98h] [rbp-218h]
  int v79; // [rsp+98h] [rbp-218h]
  size_t Size; // [rsp+A0h] [rbp-210h]
  char v81; // [rsp+D8h] [rbp-1D8h]
  char v82; // [rsp+D9h] [rbp-1D7h]
  __int64 v83; // [rsp+E0h] [rbp-1D0h] BYREF
  char v84; // [rsp+E8h] [rbp-1C8h]
  void *v85; // [rsp+F0h] [rbp-1C0h] BYREF
  char v86; // [rsp+F8h] [rbp-1B8h]
  PVOID Bcb; // [rsp+100h] [rbp-1B0h] BYREF
  union _LARGE_INTEGER EndOffset; // [rsp+108h] [rbp-1A8h] BYREF
  unsigned __int64 v89; // [rsp+110h] [rbp-1A0h]
  int v90; // [rsp+118h] [rbp-198h]
  int v91; // [rsp+11Ch] [rbp-194h] BYREF
  union _LARGE_INTEGER StartOffset; // [rsp+120h] [rbp-190h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+128h] [rbp-188h] BYREF
  __int64 v94; // [rsp+130h] [rbp-180h] BYREF
  void *Buf2; // [rsp+138h] [rbp-178h]
  size_t v96; // [rsp+140h] [rbp-170h]
  _DWORD *v97; // [rsp+148h] [rbp-168h]
  __int64 v98[12]; // [rsp+158h] [rbp-158h] BYREF
  _DWORD *v99; // [rsp+1B8h] [rbp-F8h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+1C0h] [rbp-F0h] BYREF
  __int16 v101; // [rsp+1D0h] [rbp-E0h]
  __int16 v102; // [rsp+1D2h] [rbp-DEh]
  _QWORD *v103; // [rsp+1D8h] [rbp-D8h]
  __int128 v104; // [rsp+1E0h] [rbp-D0h] BYREF
  __int128 Source1; // [rsp+1F0h] [rbp-C0h] BYREF
  __int64 v106[14]; // [rsp+208h] [rbp-A8h] BYREF

  v3 = a3;
  v86 = a3;
  v97 = a1;
  v89 = a2 + 280;
  v6 = 0;
  v83 = 0;
  v94 = 393220;
  Buf2 = L"$T";
  Bcb = 0;
  v7 = 0;
  v84 = 0;
  v104 = 0;
  v91 = 0;
  v85 = 0;
  FileOffset.QuadPart = 0;
  StartOffset.QuadPart = 0;
  IoStatus = 0;
  memset(v98, 0, 0x58u);
  v8 = *(_QWORD *)(a2 + 16);
  if ( a2 == *(_QWORD *)(v8 + 6248) )
  {
    v9 = *(_QWORD *)(v8 + 6240);
    if ( !v9 )
      ExRaiseStatus(-1073741608);
  }
  else
  {
    v9 = *(_QWORD *)(a2 + 96);
  }
  NtfsAcquireExclusiveScbEx(a1, v9, 0);
  v10 = TxfFlushAndInvalidateExistingStructures((int)a1, (__int64)&v83);
  v11 = v10;
  if ( v10 )
  {
    if ( NtfsStatusDebugFlags
      && (((v10 - 294) & 0xFFFFFFFA) != 0 || v10 == 295)
      && v10 < 0xFFFFFFED
      && v10 != -1073741608
      && v10 != -1073741802
      && v10 != -1073741807 )
    {
      v6 = 1;
      if ( v10 + 2147483643 > 1 && v10 != 259 )
        NtfsStatusTraceAndDebugInternal(a1, v10, 3343498);
    }
    NtfsRaiseStatusInternal((_DWORD)a1, v11, 0, *(_QWORD *)(v9 + 184), 3343498);
  }
  if ( v83 )
  {
    NtfsReleaseFcbEx(a1, v83, 0);
    v83 = v6;
  }
  v12 = NtfsInitializeFileInDirectory((int)a1, 0, 0, 0, 1, v6, v6);
  v83 = v12;
  if ( v12 )
  {
    LOBYTE(v11) = 0;
    v81 = 0;
  }
  else
  {
    if ( (a1[109] & 0x2000) != 0 )
    {
      if ( (a1[4] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v13,
          (unsigned int)txftxfdir_c1215,
          (unsigned int)"TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      v3 = 6;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343559);
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, *(_QWORD *)(v9 + 184), 3343559);
    }
    if ( !v3 )
    {
      if ( (a1[4] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v13,
          (unsigned int)txftxfdir_c1234,
          (unsigned int)"TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343578);
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, *(_QWORD *)(v9 + 184), 3343578);
    }
    LOBYTE(v11) = 1;
    v81 = 1;
    v12 = NtfsInitializeFileInDirectory((int)a1, 0, 0, 0, 1, 1, 0);
    v83 = v12;
  }
  if ( *(_QWORD *)(v12 + 112) )
  {
    v84 = 1;
  }
  else
  {
    LOBYTE(v14) = 1;
    NtfsAddPagingIoToFcb(a1, v83, v14);
    v84 = 1;
    if ( a1 )
    {
      v90 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v90 = i;
        if ( (unsigned int)i >= 2 )
          break;
        if ( *(_QWORD *)&a1[2 * i + 12] == v83 )
          *(_QWORD *)&a1[2 * i + 12] = 0;
      }
    }
  }
  v16 = *(_DWORD *)(v83 + 176);
  if ( (v16 & 0x4000) != 0 || (v16 & 0x800) != 0 )
  {
    if ( (!a1 || (a1[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
    {
      v73 = "encrypted";
      if ( (v16 & 0x4000) == 0 )
        v73 = "compressed";
      McTemplateU0spjs_EtwWriteTransfer((_DWORD)v73, v16 & 0x4000, v14, a2, a2 + 672, (__int64)v73);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343636);
    NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, *(_QWORD *)(v9 + 184), 3343636);
    __debugbreak();
    JUMPOUT(0x14025E6E6LL);
  }
  *(_DWORD *)(v83 + 4) |= 0xA0000u;
  if ( *(_QWORD *)(v83 + 120) )
    NtfsClearPerFileQuota(a1, v83, 0);
  if ( !(_BYTE)v11 )
  {
    LOBYTE(v76) = 0;
    if ( (unsigned __int8)NtfsLookupInFileRecord(a1, v83, v83 + 8, 0, 0, 0, v76, 0, 0, v98) )
    {
      if ( *(_DWORD *)v98[0] != 16 )
      {
        if ( (!a1 || (a1[4] & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        {
          McTemplateU0spj_EtwWriteTransfer(
            v17,
            (unsigned int)txftxfdir_c1377,
            (unsigned int)"TxfInitializeTopsStream",
            a2,
            a2 + 672);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343721);
        NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3343721);
      }
      if ( (*(_BYTE *)(v98[1] + 22) & 0xA) != 0 )
      {
        v7 = 1;
      }
      else
      {
        if ( v98[5] )
        {
          LODWORD(Size) = 0;
          v18 = NtfsLookupExternalAttribute((int)a1, v83, 48, 0, 0, 0, 0, Size, (__int64)v98);
        }
        else
        {
          LOBYTE(v77) = 0;
          v18 = NtfsLookupInFileRecord(a1, v83, 0, 48, 0, 0, v77, 0, 0, v98);
        }
        if ( v18 )
          goto LABEL_63;
        v7 = 1;
      }
      while ( 1 )
      {
        NtfsCleanupAttributeContext(v17, v98);
        if ( !v7 )
          break;
        v23 = v83;
        *(_DWORD *)(v83 + 4) &= ~0x20000u;
        if ( (!a1 || (a1[4] & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        {
          McTemplateU0spj_EtwWriteTransfer(
            v23,
            (unsigned int)txftxfdir_c1534,
            (unsigned int)"TxfInitializeTopsStream",
            a2,
            a2 + 672);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343878);
        v22 = NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3343878);
LABEL_91:
        if ( *(_BYTE *)(v11 + 8) && *(_QWORD *)(v11 + 16) || (v17 = 49407, (v22 & 0xC0FF) == 0) )
        {
LABEL_63:
          while ( 1 )
          {
            if ( v98[5] )
            {
              LODWORD(Size) = 0;
              v19 = NtfsLookupExternalAttribute((int)a1, v83, 0, 0, 0, 0, 0, Size, (__int64)v98);
            }
            else
            {
              LOBYTE(v77) = 0;
              v19 = NtfsLookupInFileRecord(a1, v83, 0, 0, 0, 0, v77, 0, 0, v98);
            }
            if ( !v19 )
              break;
            v11 = v98[0];
            v20 = *(unsigned __int8 *)(v98[0] + 9);
            v17 = *(unsigned __int8 *)(v98[0] + 9);
            LOWORD(v17) = 2 * v17;
            v101 = v17;
            v102 = v17;
            v21 = (_QWORD *)(v98[0] + *(unsigned __int16 *)(v98[0] + 10));
            v103 = v21;
            if ( *(_DWORD *)v98[0] != 256 || (_WORD)v17 != 18 )
              goto LABEL_297;
            v17 = *v21 - 0x46005800540024LL;
            if ( *v21 == 0x46005800540024LL )
            {
              v17 = v21[1] - 0x5400410044005FLL;
              if ( v21[1] == 0x5400410044005FLL )
                v17 = *((unsigned __int16 *)v21 + 8) - 65LL;
            }
            if ( v17 )
            {
LABEL_297:
              if ( *(_DWORD *)v98[0] == 128
                && (!(_BYTE)v20 || v20 == (unsigned __int16)v94 >> 1 && !memcmp(v21, Buf2, (unsigned __int16)v94)) )
              {
                v22 = *(_WORD *)(v11 + 12);
                v17 = 16639;
                if ( (v22 & 0x40FF) == 0 )
                  goto LABEL_91;
              }
              goto LABEL_81;
            }
            if ( a2 == *(_QWORD *)(*(_QWORD *)(a2 + 16) + 6248LL) )
              DbgPrintEx(
                0x82u,
                0,
                "%s:%d -- TxF corruption detected, %s == 0x%x",
                "TxfTxfDir.c",
                1455,
                "Status",
                -1072103418);
          }
        }
        else
        {
LABEL_81:
          v7 = 1;
        }
        LOBYTE(v11) = v81;
      }
    }
    else
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v17,
          (unsigned int)txftxfdir_c1390,
          (unsigned int)"TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343734);
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3343734);
    }
  }
  memset(v98, 0, 0x58u);
  LOWORD(v104) = 0;
  v24 = 2 * ((unsigned __int8)v11 ^ 1);
  v25 = a2 + 288;
  Attribute = NtOfsCreateAttributeEx((_DWORD)a1, v83, (unsigned int)&v104, 128, v24, 1, a2 + 288);
  v28 = Attribute;
  if ( Attribute )
  {
    if ( !v81 && Attribute == -1073741772 )
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v27,
          (unsigned int)txftxfdir_c1589,
          (unsigned int)"TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343933);
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3343933);
    }
    if ( NtfsStatusDebugFlags
      && (((v28 - 294) & 0xFFFFFFFA) != 0 || v28 == 295)
      && v28 < 0xFFFFFFED
      && v28 != -1073741608
      && v28 != -1073741802
      && v28 != -1073741807
      && v28 + 2147483643 > 1
      && v28 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v28, 3343938);
    }
    NtfsRaiseStatusInternal((_DWORD)a1, v28, 0, v83, 3343938);
  }
  v29 = 0;
  LOBYTE(v78) = 0;
  if ( !(unsigned __int8)NtfsLookupInFileRecord(
                           a1,
                           *(_QWORD *)(*(_QWORD *)v25 + 184LL),
                           *(_QWORD *)(*(_QWORD *)v25 + 184LL) + 8LL,
                           *(unsigned int *)(*(_QWORD *)v25 + 256LL),
                           *(_QWORD *)v25 + 264LL,
                           0,
                           v78,
                           0,
                           0,
                           v98)
    && (*(_DWORD *)(*(_QWORD *)v25 + 512LL) & 4) == 0 )
  {
    v29 = 0xA90033064CLL;
    NtfsAttachCorruption_BadOrOrphanFRS(
      (_DWORD)a1,
      2,
      3343948,
      v30,
      *(_QWORD *)(*(_QWORD *)v25 + 184LL) + 8LL,
      *(_QWORD *)(*(_QWORD *)v25 + 184LL),
      0);
    NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA90033064CLL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3343948);
    NtfsRaiseStatusInternal(
      (_DWORD)a1,
      -1073741566,
      *(_QWORD *)(*(_QWORD *)(v89 + 8) + 184LL) + 8,
      *(_QWORD *)(*(_QWORD *)(v89 + 8) + 184LL),
      3343948);
  }
  NtfsMapAttributeValue(a1, v83, &v85, &v91, &Bcb, v98);
  if ( v81 == (_BYTE)v29 )
  {
    v31 = v85;
    v32 = (char *)v85 + 8;
    *(_OWORD *)(a2 + 672) = *(_OWORD *)((char *)v85 + 8);
    if ( !v86 )
    {
      if ( v91 == 100 )
      {
        if ( *v31 == 10 && v31[1] == 100 )
        {
LABEL_157:
          if ( Bcb )
          {
            CcUnpinData(Bcb);
            Bcb = 0;
          }
          v34 = v85;
          *(_QWORD *)(a2 + 408) = *((_QWORD *)v85 + 4);
          *(_DWORD *)(a2 + 128) |= 2u;
          *(_QWORD *)(a2 + 432) = v34[6];
          KeWaitForSingleObject(*(PVOID *)(a2 + 544), Executive, 0, 0, 0);
          *(_QWORD *)(a2 + 536) = *((_QWORD *)v85 + 7);
          KeReleaseMutex(*(PRKMUTEX *)(a2 + 544), 0);
          *(_QWORD *)(a2 + 440) = *((_QWORD *)v85 + 7);
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 24) + 472LL));
          *(_QWORD *)(a2 + 688) = *((_QWORD *)v85 + 5);
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 24) + 472LL));
          v35 = *(unsigned int *)(a2 + 584);
          if ( *((_DWORD *)v85 + 1) != (_DWORD)v35 )
          {
            if ( (!a1 || (a1[4] & 0x100000) == 0)
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
            {
              McTemplateU0spj_EtwWriteTransfer(
                v35,
                (unsigned int)txftxfdir_c1764,
                (unsigned int)"TxfInitializeTopsStream",
                a2,
                a2 + 672);
            }
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3344108);
            NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3344108);
          }
          v36 = a2 + 280;
          goto LABEL_175;
        }
        if ( (!a1 || (a1[4] & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        {
          McTemplateU0spj_EtwWriteTransfer(
            (_DWORD)v31,
            (unsigned int)txftxfdir_c1651,
            (unsigned int)"TxfInitializeTopsStream",
            a2,
            a2 + 672);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343995);
        NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3343995);
      }
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          (_DWORD)v31,
          (unsigned int)txftxfdir_c1666,
          (unsigned int)"TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3344010);
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3344010);
    }
    Source1 = 0;
    if ( RtlCompareMemory(&Source1, v32, 0x10u) != 16 )
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v33,
          (unsigned int)txftxfdir_c1691,
          (unsigned int)"TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3344035);
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3344035);
    }
    goto LABEL_157;
  }
  memset(v106, 0, 0x64u);
  v37 = v106;
  v85 = v106;
  if ( v98[2] == v29 )
  {
    v98[2] = (__int64)Bcb;
    Bcb = (PVOID)v29;
  }
  else if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = (PVOID)v29;
    v37 = v85;
  }
  memset(v37, 0, 0x64u);
  *(_WORD *)v85 = 10;
  *((_WORD *)v85 + 1) = 100;
  *((_DWORD *)v85 + 20) = -1;
  *((_DWORD *)v85 + 21) = -1;
  *((_DWORD *)v85 + 22) = -1;
  *((_WORD *)v85 + 48) = -1;
  *((_WORD *)v85 + 49) = -1;
  if ( a2 != *(_QWORD *)(*(_QWORD *)(a2 + 16) + 6248LL) )
  {
    ++*(_DWORD *)(a2 + 584);
    TxfUpdateTxfDataAttributeMembers(
      (int)a1,
      *(_QWORD *)(*(_QWORD *)(a2 + 96) + 184LL),
      (int)Timeout,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      a2 + 584);
    NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(a2 + 80), 0);
    LOBYTE(v29) = 0;
    TxfUpdateTxfDataAttributeMembers(
      (int)a1,
      *(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL),
      Timeouta,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      a2 + 584);
  }
  *((_DWORD *)v85 + 1) = *(_DWORD *)(a2 + 584);
  *((CLFS_LSN *)v85 + 4) = CLFS_LSN_INVALID_EXT;
  *(CLFS_LSN *)(a2 + 408) = CLFS_LSN_INVALID_EXT;
  LODWORD(Timeout) = *((unsigned __int16 *)v85 + 1);
  NtfsChangeAttributeValue((int)a1, v83, 0, (int)v85, (SIZE_T)Timeout, 1, 1, v29, v29, v98);
  v36 = a2 + 280;
  ClearFlagInterlocked(*(_QWORD *)(a2 + 288) + 200LL, 544);
  NtfsUpdateScbFromAttribute(a1, *(_QWORD *)(a2 + 288), v98[0]);
LABEL_175:
  v82 = 0;
  NtfsCleanupAttributeContext(v35, v98);
  memset(v98, 0, 0x58u);
  v38 = NtOfsCreateAttributeEx((_DWORD)a1, v83, (unsigned int)&v94, 128, v24, 1, v36);
  v40 = v38;
  if ( v38 )
  {
    if ( !v81 && v38 == -1073741772 )
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v39,
          (unsigned int)txftxfdir_c1905,
          (unsigned int)"TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3344249);
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v83, 3344249);
    }
    if ( NtfsStatusDebugFlags
      && (((v40 - 294) & 0xFFFFFFFA) != 0 || v40 == 295)
      && v40 < 0xFFFFFFED
      && v40 != -1073741608
      && v40 != -1073741802
      && v40 != -1073741807
      && v40 + 2147483643 > 1
      && v40 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v40, 3344254);
    }
    NtfsRaiseStatusInternal((_DWORD)a1, v40, 0, v83, 3344254);
  }
  v41 = *(_QWORD *)(a2 + 280);
  if ( (*(_DWORD *)(v41 + 200) & 0x20) == 0 )
    NtfsUpdateScbFromAttribute(a1, *(_QWORD *)(a2 + 280), 0);
  if ( (*(_DWORD *)(v41 + 200) & 8) != 0 )
  {
    v82 = 1;
    LOBYTE(v79) = 0;
    if ( !(unsigned __int8)NtfsLookupInFileRecord(
                             a1,
                             *(_QWORD *)(v41 + 184),
                             *(_QWORD *)(v41 + 184) + 8LL,
                             *(unsigned int *)(v41 + 256),
                             v41 + 264,
                             0,
                             v79,
                             0,
                             0,
                             v98)
      && (*(_DWORD *)(v41 + 512) & 4) == 0 )
    {
      NtfsAttachCorruption_BadOrOrphanFRS(
        (_DWORD)a1,
        2,
        3344283,
        v42,
        *(_QWORD *)(v41 + 184) + 8LL,
        *(_QWORD *)(v41 + 184),
        0);
      NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA90033079BLL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3344283);
      NtfsRaiseStatusInternal((_DWORD)a1, -1073741566, *(_QWORD *)(v41 + 184) + 8, *(_QWORD *)(v41 + 184), 3344283);
    }
    NtfsConvertToNonresident((__int64)a1, v83, v98[0], 1u, v98);
  }
  NtfsPreloadAllocationInternal((_DWORD)a1, 0x7FFFFFFFFFFFFFFFLL, 0);
  v43 = (signed __int64 *)(v41 + 24);
  v44 = *(_QWORD *)(v41 + 24);
  if ( v44 < 0x100000 )
    NtfsAddAllocation(
      (_DWORD)a1,
      ((*(unsigned int *)(*(_QWORD *)(a2 + 16) + 480LL) + 0x100000LL) >> *(_BYTE *)(*(_QWORD *)(a2 + 16) + 488LL))
    - ((v44 + *(unsigned int *)(*(_QWORD *)(a2 + 16) + 480LL)) >> *(_BYTE *)(*(_QWORD *)(a2 + 16) + 488LL)),
      0,
      0);
  v89 = ((*v43 + 4095) / 4096) & 0xFFFFFFF8LL;
  QuadPart = v89 >> 3;
  EndOffset.QuadPart = v89 >> 3;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v89 >> 3, 0x62547854u);
  *(_QWORD *)(a2 + 312) = PoolWithTag;
  memset(PoolWithTag, 0, QuadPart);
  v47 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), QuadPart, 0x62547854u);
  v48 = v47;
  *(_QWORD *)(a2 + 328) = v47;
  v99 = v47;
  v49 = QuadPart >> 2;
  v96 = QuadPart >> 2;
  if ( QuadPart >> 2 )
  {
    if ( ((unsigned __int8)v47 & 4) != 0 )
    {
      *v47 = -1;
      v96 = --v49;
      if ( !v49 )
        goto LABEL_214;
      v48 = v47 + 1;
      v99 = v47 + 1;
    }
    memset(v48, 0xFFu, 8 * (v49 >> 1));
    if ( (v49 & 1) != 0 )
      *((_DWORD *)v48 + v49 - 1) = -1;
    QuadPart = EndOffset.QuadPart;
  }
LABEL_214:
  v50 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), QuadPart, 0x62547854u);
  *(_QWORD *)(a2 + 344) = v50;
  memset(v50, 0, QuadPart);
  v51 = v89;
  v52 = a2 + 280;
  *(_DWORD *)(a2 + 304) = v89;
  *(_DWORD *)(a2 + 320) = v51;
  *(_DWORD *)(a2 + 336) = v51;
  *(_DWORD *)(a2 + 300) = v51;
  *(_DWORD *)(a2 + 296) = 0;
  *(_WORD *)(a2 + 352) = -1;
  NtfsCreateInternalAttributeStream((__int64)a1, v41, 0, 8, 0, 0);
  CcSetAdditionalCacheAttributes(*(PFILE_OBJECT *)(v41 + 280), 0, 1u);
  v54 = *(_DWORD *)(v41 + 200);
  if ( (v54 & 0x20000) != 0 )
  {
    v55 = *v43;
    if ( *(_QWORD *)(v41 + 32) < *v43 )
    {
      if ( v55 >= *(_QWORD *)(v41 + 464) )
        v55 = *(_QWORD *)(v41 + 464);
      v56 = *(_QWORD *)(v41 + 40);
      if ( v55 > v56 )
      {
        if ( (v54 & 0x200) != 0 )
          v56 = *(_QWORD *)(v41 + 40);
        v57 = *(_DWORD *)(v41 + 200);
        if ( (v57 & 0x20000) == 0 )
          goto LABEL_229;
        v58 = *(_QWORD *)(v41 + 464);
        if ( v58 >= v55 )
        {
          if ( v56 <= v55 )
          {
LABEL_229:
            *(_QWORD *)(v41 + 40) = v55;
            goto LABEL_231;
          }
          if ( *(_QWORD *)(*(_QWORD *)(v41 + 288) + 16LL) && v55 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v59 = (v55 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v59 < v58 )
              *(_QWORD *)(v41 + 464) = v59;
            v52 = a2 + 280;
            goto LABEL_229;
          }
        }
        *(_QWORD *)(v41 + 464) = v55;
        goto LABEL_229;
      }
    }
  }
LABEL_231:
  *(_QWORD *)(v41 + 32) = *v43;
  LOBYTE(v53) = 1;
  NtfsWriteFileSizes((_DWORD)a1, v41, 0, v53, 1, 1);
  NtfsCheckpointCurrentTransaction(a1);
  if ( v81 )
    NtfsSetCcFileSizes(*(_QWORD *)(*(_QWORD *)(v52 + 8) + 280LL), *(_QWORD *)(v52 + 8), *(_QWORD *)(v52 + 8) + 24LL);
  NtfsSetCcFileSizes(*(_QWORD *)(v41 + 280), v41, v41 + 24);
  v62 = *(union _LARGE_INTEGER *)(v41 + 40);
  if ( v62.QuadPart != *(_QWORD *)(v41 + 32) )
  {
    FileOffset = *(union _LARGE_INTEGER *)(v41 + 40);
    v63.QuadPart = *(_QWORD *)(v41 + 32) - 1LL;
    v89 = v63.QuadPart;
    StartOffset = v62;
    while ( v62.QuadPart <= v63.QuadPart )
    {
      EndOffset.QuadPart = v62.QuadPart + 4095;
      if ( v62.QuadPart + 4095 > v63.QuadPart )
        EndOffset = v63;
      CcZeroData(*(PFILE_OBJECT *)(v41 + 280), &StartOffset, &EndOffset, 1u);
      v62.QuadPart = EndOffset.QuadPart + 1;
      StartOffset.QuadPart = EndOffset.QuadPart + 1;
    }
    v64 = v63.QuadPart + 1;
    v89 = v64;
    FsRtlAcquireHeaderMutex(v41 + 120, v41 + 160, v61);
    v65 = *(_DWORD *)(v41 + 200);
    if ( (v65 & 0x20000) == 0 )
      goto LABEL_248;
    v66 = *(_QWORD *)(v41 + 32);
    v67 = *(_QWORD *)(v41 + 464);
    if ( v67 >= v66 )
    {
      if ( *(_QWORD *)(v41 + 40) <= v66 )
        goto LABEL_248;
      if ( *(_QWORD *)(*(_QWORD *)(v41 + 288) + 16LL) && v66 != 0x7FFFFFFFFFFFFFFFLL )
      {
        if ( (__int64)((v66 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v67 )
        {
          v68 = (*(_QWORD *)(v41 + 32) + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
LABEL_247:
          *(_QWORD *)(v41 + 464) = v68;
        }
LABEL_248:
        *(_QWORD *)(v41 + 40) = *(_QWORD *)(v41 + 32);
        FsRtlReleaseHeaderMutex(v41 + 120, v41 + 160);
        CcFlushCache(
          (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v41 + 288) + 16LL),
          &FileOffset,
          v64 - FileOffset.LowPart,
          &IoStatus);
        if ( IoStatus.Status < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)(IoStatus.Status - 298) > 1
            && IoStatus.Status < 0xFFFFFFED
            && IoStatus.Status != -1073741608
            && IoStatus.Status != -1073741802
            && IoStatus.Status != -1073741807
            && (unsigned int)(IoStatus.Status + 2147483643) > 1 )
          {
            NtfsStatusTraceAndDebugInternal(a1, (unsigned int)IoStatus.Status, 3344480);
          }
          NtfsRaiseStatusInternal(
            (_DWORD)a1,
            IoStatus.Status,
            *(_QWORD *)(v41 + 184) + 8,
            *(_QWORD *)(v41 + 184),
            3344480);
        }
        LOBYTE(v69) = 1;
        NtfsWriteFileSizes((_DWORD)a1, v41, 0, v69, 1, 1);
        NtfsCheckpointCurrentTransaction(a1);
        goto LABEL_259;
      }
    }
    v68 = *(_QWORD *)(v41 + 32);
    goto LABEL_247;
  }
LABEL_259:
  if ( *(_QWORD *)(v83 + 320) != a2 )
  {
    if ( a2 )
    {
      _InterlockedAdd((volatile signed __int32 *)(a2 + 64), 1u);
      _InterlockedAdd((volatile signed __int32 *)(a2 + 36), 1u);
    }
    v60 = *(_QWORD *)(v83 + 320);
    if ( v60 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v60 + 36));
      v60 = *(_QWORD *)(v83 + 320);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v60 + 64), 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb(*(char **)(v83 + 320));
    }
    *(_QWORD *)(v83 + 320) = a2;
  }
  if ( v84 )
  {
    if ( a1 && a1[7] )
    {
      for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
      {
        v60 = (unsigned int)j;
        v71 = *(_QWORD *)&a1[2 * j + 12];
        if ( !v71 || v71 == v83 )
        {
          *(_QWORD *)&a1[2 * (unsigned int)j + 12] = v83;
          break;
        }
      }
    }
    else
    {
      NtfsReleasePagingResourcePriv(v60, v83);
      if ( a1 )
      {
        v72 = 0;
        v60 = v83;
        do
        {
          if ( *(_QWORD *)&a1[2 * v72 + 12] == v60 )
            *(_QWORD *)&a1[2 * v72 + 12] = 0;
          ++v72;
        }
        while ( v72 != 2 );
      }
    }
  }
  if ( v82 )
    NtfsCleanupAttributeContext(v60, v98);
  if ( Bcb )
    CcUnpinData(Bcb);
}

```

## disassembly

```asm
0x14025ccec  mov     r11, rsp
0x14025ccef  mov     [r11+18h], rbx
0x14025ccf3  mov     [r11+20h], rsi
0x14025ccf7  push    rdi
0x14025ccf8  push    r12
0x14025ccfa  push    r13
0x14025ccfc  push    r14
0x14025ccfe  push    r15
0x14025cd00  sub     rsp, 220h
0x14025cd07  mov     rax, cs:__security_cookie
0x14025cd0e  xor     rax, rsp
0x14025cd11  mov     [rsp+248h+var_38], rax
0x14025cd19  mov     sil, r8b
0x14025cd1c  mov     [rsp+248h+var_1B8], r8b
0x14025cd24  mov     r14, rdx
0x14025cd27  mov     rbx, rcx
0x14025cd2a  mov     [rsp+248h+var_168], rcx
0x14025cd32  lea     rax, [rdx+118h]
0x14025cd39  mov     [rsp+248h+var_1A0], rax
0x14025cd41  xor     r15d, r15d
0x14025cd44  mov     [rsp+248h+var_1D0], r15
0x14025cd49  mov     qword ptr [r11-180h], 60004h
0x14025cd54  lea     rax, aT; "$T"
0x14025cd5b  mov     [r11-178h], rax
0x14025cd62  mov     [r11-1B0h], r15
0x14025cd69  mov     r12b, r15b
0x14025cd6c  mov     [r11-1C8h], r15b
0x14025cd73  xorps   xmm0, xmm0
0x14025cd76  movups  [rsp+248h+var_D0], xmm0
0x14025cd7e  mov     [r11-194h], r15d
0x14025cd85  mov     [r11-1C0h], r15
0x14025cd8c  mov     [r11-188h], r15
0x14025cd93  mov     [r11-190h], r15
0x14025cd9a  movups  xmmword ptr [rsp+248h+IoStatus], xmm0
0x14025cda2  mov     [rsp+248h+var_1D7], r15b
0x14025cda7  xor     edx, edx; Val
0x14025cda9  lea     r8d, [r15+58h]; Size
0x14025cdad  lea     rcx, [r11-158h]; void *
0x14025cdb4  call    memset
0x14025cdb9  nop
0x14025cdba  mov     r13, [r14+10h]
0x14025cdbe  cmp     r14, [r13+1868h]
0x14025cdc5  jnz     short loc_14025CDEA
0x14025cdc7  mov     r13, [r13+1860h]
0x14025cdce  test    r13, r13
0x14025cdd1  jnz     short loc_14025CDEE
0x14025cdd3  mov     al, cs:NtfsStatusDebugFlags
0x14025cdd9  mov     ecx, 0C00000D8h; Status
0x14025cdde  call    cs:__imp_ExRaiseStatus
0x14025cdea  mov     r13, [r14+60h]
0x14025cdee  xor     r8d, r8d
0x14025cdf1  mov     rdx, r13
0x14025cdf4  mov     rcx, rbx
0x14025cdf7  call    NtfsAcquireExclusiveScbEx
0x14025cdfc  lea     rax, [rsp+248h+var_1D0]
0x14025ce01  mov     [rsp+248h+Timeout], rax; __int64
0x14025ce06  xor     r9d, r9d
0x14025ce09  lea     r8, NtfsTopsName
0x14025ce10  mov     rdx, r13
0x14025ce13  mov     rcx, rbx; int
0x14025ce16  call    TxfFlushAndInvalidateExistingStructures
0x14025ce1b  mov     edi, eax
0x14025ce1d  test    eax, eax
0x14025ce1f  jz      loc_14025CEA6
0x14025ce25  mov     cl, cs:NtfsStatusDebugFlags
0x14025ce2b  test    cl, cl
0x14025ce2d  jz      short loc_14025CE89
0x14025ce2f  lea     ecx, [rax-126h]
0x14025ce35  test    ecx, 0FFFFFFFAh
0x14025ce3b  jnz     short loc_14025CE44
0x14025ce3d  cmp     eax, 127h
0x14025ce42  jnz     short loc_14025CE89
0x14025ce44  cmp     edi, 0FFFFFFEDh
0x14025ce47  jnb     short loc_14025CE89
0x14025ce49  cmp     edi, 0C00000D8h
0x14025ce4f  jz      short loc_14025CE89
0x14025ce51  cmp     edi, 0C0000016h
0x14025ce57  jz      short loc_14025CE89
0x14025ce59  cmp     edi, 0C0000011h
0x14025ce5f  jz      short loc_14025CE89
0x14025ce61  add     eax, 7FFFFFFBh
0x14025ce66  mov     r15d, 1
0x14025ce6c  cmp     eax, r15d
0x14025ce6f  jbe     short loc_14025CE89
0x14025ce71  cmp     edi, 103h
0x14025ce77  jz      short loc_14025CE89
0x14025ce79  mov     r8d, 33048Ah
0x14025ce7f  mov     edx, edi
0x14025ce81  mov     rcx, rbx
0x14025ce84  call    NtfsStatusTraceAndDebugInternal
0x14025ce89  mov     [rsp+248h+Timeout], 33048Ah
0x14025ce92  mov     r9, [r13+0B8h]
0x14025ce99  xor     r8d, r8d
0x14025ce9c  mov     edx, edi
0x14025ce9e  mov     rcx, rbx
0x14025cea1  call    NtfsRaiseStatusInternal
0x14025cea6  mov     rdx, [rsp+248h+var_1D0]
0x14025ceab  test    rdx, rdx
0x14025ceae  jz      short loc_14025CEC0
0x14025ceb0  xor     r8d, r8d
0x14025ceb3  mov     rcx, rbx
0x14025ceb6  call    NtfsReleaseFcbEx
0x14025cebb  mov     [rsp+248h+var_1D0], r15
0x14025cec0  mov     dword ptr [rsp+248h+var_200], r15d; int
0x14025cec5  mov     dword ptr [rsp+248h+var_208], r15d; int
0x14025ceca  mov     r15d, 1
0x14025ced0  mov     byte ptr [rsp+248h+Size], r15b; char
0x14025ced5  xor     eax, eax
0x14025ced7  mov     byte ptr [rsp+248h+var_218], al; char
0x14025cedb  mov     [rsp+248h+IgnoreCase], al; char
0x14025cedf  mov     byte ptr [rsp+248h+Timeout], al; char
0x14025cee3  lea     r9, NtfsTopsName
0x14025ceea  xor     r8d, r8d
0x14025ceed  mov     rdx, r13
0x14025cef0  mov     rcx, rbx; int
0x14025cef3  call    NtfsInitializeFileInDirectory
0x14025cef8  mov     [rsp+248h+var_1D0], rax
0x14025cefd  test    rax, rax
0x14025cf00  jnz     loc_14025D03E
0x14025cf06  test    dword ptr [rbx+1B4h], 2000h
0x14025cf10  jz      short loc_14025CF83
0x14025cf12  mov     eax, [rbx+10h]
0x14025cf15  bt      rax, 14h
0x14025cf1a  jb      short loc_14025CF47
0x14025cf1c  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 8
0x14025cf23  jz      short loc_14025CF47
0x14025cf25  lea     rax, [r14+2A0h]
0x14025cf2c  mov     [rsp+248h+Timeout], rax
0x14025cf31  mov     r9, r14
0x14025cf34  lea     r8, aTxfinitializet; "TxfInitializeTopsStream"
0x14025cf3b  lea     rdx, txftxfdir_c1215
0x14025cf42  call    McTemplateU0spj_EtwWriteTransfer
0x14025cf47  mov     al, cs:NtfsStatusDebugFlags
0x14025cf4d  mov     esi, 0C0190006h
0x14025cf52  test    al, al
0x14025cf54  jz      short loc_14025CF66
0x14025cf56  mov     r8d, 3304C7h
0x14025cf5c  mov     edx, esi
0x14025cf5e  mov     rcx, rbx
0x14025cf61  call    NtfsStatusTraceAndDebugInternal
0x14025cf66  mov     [rsp+248h+Timeout], 3304C7h
0x14025cf6f  mov     r9, [r13+0B8h]
0x14025cf76  xor     r8d, r8d
0x14025cf79  mov     edx, esi
0x14025cf7b  mov     rcx, rbx
0x14025cf7e  call    NtfsRaiseStatusInternal
0x14025cf83  test    sil, sil
0x14025cf86  jnz     short loc_14025CFF9
0x14025cf88  mov     eax, [rbx+10h]
0x14025cf8b  bt      rax, 14h
0x14025cf90  jb      short loc_14025CFBD
0x14025cf92  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 8
0x14025cf99  jz      short loc_14025CFBD
0x14025cf9b  lea     rax, [r14+2A0h]
0x14025cfa2  mov     [rsp+248h+Timeout], rax
0x14025cfa7  mov     r9, r14
0x14025cfaa  lea     r8, aTxfinitializet; "TxfInitializeTopsStream"
0x14025cfb1  lea     rdx, txftxfdir_c1234
0x14025cfb8  call    McTemplateU0spj_EtwWriteTransfer
0x14025cfbd  mov     al, cs:NtfsStatusDebugFlags
0x14025cfc3  mov     esi, 0C0190006h
0x14025cfc8  test    al, al
0x14025cfca  jz      short loc_14025CFDC
0x14025cfcc  mov     r8d, 3304DAh
0x14025cfd2  mov     edx, esi
0x14025cfd4  mov     rcx, rbx
0x14025cfd7  call    NtfsStatusTraceAndDebugInternal
0x14025cfdc  mov     [rsp+248h+Timeout], 3304DAh
0x14025cfe5  mov     r9, [r13+0B8h]
0x14025cfec  xor     r8d, r8d
0x14025cfef  mov     edx, esi
0x14025cff1  mov     rcx, rbx
0x14025cff4  call    NtfsRaiseStatusInternal
0x14025cff9  mov     dil, r15b
0x14025cffc  mov     [rsp+248h+var_1D8], r15b
0x14025d001  mov     dword ptr [rsp+248h+var_200], 0; int
0x14025d009  mov     dword ptr [rsp+248h+var_208], r15d; int
0x14025d00e  mov     byte ptr [rsp+248h+Size], r15b; char
0x14025d013  mov     byte ptr [rsp+248h+var_218], 0; char
0x14025d018  mov     [rsp+248h+IgnoreCase], 0; char
0x14025d01d  mov     byte ptr [rsp+248h+Timeout], 0; char
0x14025d022  lea     r9, NtfsTopsName
0x14025d029  xor     r8d, r8d
0x14025d02c  mov     rdx, r13
0x14025d02f  mov     rcx, rbx; int
0x14025d032  call    NtfsInitializeFileInDirectory
0x14025d037  mov     [rsp+248h+var_1D0], rax
0x14025d03c  jmp     short loc_14025D046
0x14025d03e  xor     dil, dil
0x14025d041  mov     [rsp+248h+var_1D8], dil
0x14025d046  cmp     qword ptr [rax+70h], 0
0x14025d04b  jnz     short loc_14025D09D
0x14025d04d  mov     r8b, r15b
0x14025d050  mov     rdx, [rsp+248h+var_1D0]
0x14025d055  mov     rcx, rbx
0x14025d058  call    NtfsAddPagingIoToFcb
0x14025d05d  mov     [rsp+248h+var_1C8], r15b
0x14025d065  test    rbx, rbx
0x14025d068  jz      short loc_14025D0A5
0x14025d06a  mov     [rsp+248h+var_198], 0
0x14025d075  xor     ecx, ecx
0x14025d077  mov     [rsp+248h+var_198], ecx
0x14025d07e  cmp     ecx, 2
0x14025d081  jnb     short loc_14025D0A5
0x14025d083  mov     rax, [rsp+248h+var_1D0]
0x14025d088  cmp     [rbx+rcx*8+30h], rax
0x14025d08d  jnz     short loc_14025D098
0x14025d08f  mov     qword ptr [rbx+rcx*8+30h], 0
0x14025d098  add     ecx, r15d
0x14025d09b  jmp     short loc_14025D077
0x14025d09d  mov     [rsp+248h+var_1C8], r15b
0x14025d0a5  mov     rcx, [rsp+248h+var_1D0]
0x14025d0aa  mov     eax, [rcx+0B0h]
0x14025d0b0  mov     edx, eax
0x14025d0b2  and     edx, 4000h
0x14025d0b8  jnz     loc_14025E663
0x14025d0be  bt      eax, 0Bh
0x14025d0c2  jb      loc_14025E663
0x14025d0c8  mov     eax, [rcx+4]
0x14025d0cb  or      eax, 0A0000h
0x14025d0d0  mov     [rcx+4], eax
0x14025d0d3  mov     eax, [rcx+4]
0x14025d0d6  mov     rdx, [rsp+248h+var_1D0]
0x14025d0db  xor     r13d, r13d
0x14025d0de  cmp     [rdx+78h], r13
0x14025d0e2  jz      short loc_14025D0EF
0x14025d0e4  xor     r8d, r8d
0x14025d0e7  mov     rcx, rbx
0x14025d0ea  call    NtfsClearPerFileQuota
0x14025d0ef  test    dil, dil
0x14025d0f2  jnz     loc_14025D52A
0x14025d0f8  mov     [rsp+248h+var_1D7], r15b
0x14025d0fd  mov     rdx, [rsp+248h+var_1D0]
0x14025d102  lea     r8, [rdx+8]
0x14025d106  lea     rax, [rsp+248h+var_158]
0x14025d10e  mov     [rsp+248h+var_200], rax
0x14025d113  mov     dword ptr [rsp+248h+var_208], r13d
0x14025d118  mov     [rsp+248h+Size], r13
0x14025d11d  mov     byte ptr [rsp+248h+var_218], r13b
0x14025d122  mov     qword ptr [rsp+248h+IgnoreCase], r13
0x14025d127  mov     [rsp+248h+Timeout], r13
0x14025d12c  xor     r9d, r9d
0x14025d12f  mov     rcx, rbx
0x14025d132  call    NtfsLookupInFileRecord
0x14025d137  test    al, al
0x14025d139  jz      loc_14025D4B6
0x14025d13f  mov     rax, [rsp+248h+var_158]
0x14025d147  cmp     dword ptr [rax], 10h
0x14025d14a  jz      short loc_14025D1C0
0x14025d14c  test    rbx, rbx
0x14025d14f  jz      short loc_14025D15B
0x14025d151  mov     eax, [rbx+10h]
0x14025d154  bt      rax, 14h
0x14025d159  jb      short loc_14025D186
0x14025d15b  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 8
0x14025d162  jz      short loc_14025D186
0x14025d164  lea     rax, [r14+2A0h]
0x14025d16b  mov     [rsp+248h+Timeout], rax
0x14025d170  mov     r9, r14
0x14025d173  lea     r8, aTxfinitializet; "TxfInitializeTopsStream"
0x14025d17a  lea     rdx, txftxfdir_c1377
0x14025d181  call    McTemplateU0spj_EtwWriteTransfer
0x14025d186  mov     al, cs:NtfsStatusDebugFlags
0x14025d18c  mov     esi, 0C0190006h
0x14025d191  test    al, al
0x14025d193  jz      short loc_14025D1A5
0x14025d195  mov     r8d, 330569h
0x14025d19b  mov     edx, esi
0x14025d19d  mov     rcx, rbx
0x14025d1a0  call    NtfsStatusTraceAndDebugInternal
0x14025d1a5  mov     [rsp+248h+Timeout], 330569h
0x14025d1ae  mov     r9, [rsp+248h+var_1D0]
0x14025d1b3  xor     r8d, r8d
0x14025d1b6  mov     edx, esi
0x14025d1b8  mov     rcx, rbx
0x14025d1bb  call    NtfsRaiseStatusInternal
0x14025d1c0  mov     rax, [rsp+248h+var_150]
0x14025d1c8  test    byte ptr [rax+16h], 0Ah
0x14025d1cc  jnz     loc_14025D4A9
0x14025d1d2  lea     rax, [rsp+248h+var_158]
0x14025d1da  mov     rdx, [rsp+248h+var_1D0]; int
0x14025d1df  mov     rcx, rbx; int
0x14025d1e2  cmp     [rsp+248h+var_130], r13
0x14025d1ea  jnz     short loc_14025D21A
0x14025d1ec  mov     [rsp+248h+var_200], rax
0x14025d1f1  mov     dword ptr [rsp+248h+var_208], r13d
0x14025d1f6  mov     [rsp+248h+Size], r13
0x14025d1fb  mov     byte ptr [rsp+248h+var_218], r13b
0x14025d200  mov     qword ptr [rsp+248h+IgnoreCase], r13
0x14025d205  mov     [rsp+248h+Timeout], r13
0x14025d20a  mov     r9d, 30h ; '0'
0x14025d210  xor     r8d, r8d
0x14025d213  call    NtfsLookupInFileRecord
0x14025d218  jmp     short loc_14025D23F
0x14025d21a  mov     qword ptr [rsp+248h+var_208], rax; __int64
0x14025d21f  mov     dword ptr [rsp+248h+Size], r13d; Size
0x14025d224  mov     [rsp+248h+var_218], r13; void *
0x14025d229  mov     [rsp+248h+IgnoreCase], r13b; IgnoreCase
0x14025d22e  mov     [rsp+248h+Timeout], r13; __int64
0x14025d233  xor     r9d, r9d; ConstantNameB
  ... truncated ...
```
