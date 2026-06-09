# TxfInitializeTopsStream

- ea: `0x14025cc9c`
- end: `0x14025e696`
- name: `TxfInitializeTopsStream`
- size: `6650`
- prototype: `void __fastcall(_DWORD *, __int64, char)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14025a2c8`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000ea70`
- `0x140012e70`
- `0x140021590`
- `0x1400410a8`
- `0x140049c90`
- `0x140054228`
- `0x140059250`
- `0x1400596c0`
- `0x140059be0`
- `0x1400e3340`
- `0x1401250b0`
- `0x140125f70`
- `0x1401261d0`
- `0x140128d50`
- `0x14013c2d0`
- `0x140140380`
- `0x1401436e0`
- `0x140145d8c`
- `0x140150bc0`
- `0x140150c80`
- `0x1401580e0`
- `0x140159768`
- `0x140160be0`
- `0x1401620c0`
- `0x140163f78`
- `0x140165c10`
- `0x1401913d4`
- `0x140196e30`
- `0x1401e0660`
- `0x1401fd820`
- `0x14025cc9c`
- `0x14025e69c`

## import_xrefs

- `ntoskrnl!CcZeroData` at `0x14025e2fa`
- `ntoskrnl!CcZeroData` at `0x14025e2fa`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14025e13a`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14025e13a`
- `ntoskrnl!KeReleaseMutex` at `0x14025d9ae`
- `ntoskrnl!KeReleaseMutex` at `0x14025d9ae`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14025e3f0`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14025e3f0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14025e334`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14025e334`
- `ntoskrnl!DbgPrintEx` at `0x14025d32d`
- `ntoskrnl!DbgPrintEx` at `0x14025d32d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14025d986`
- `ntoskrnl!KeWaitForSingleObject` at `0x14025d986`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e002`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e034`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e0ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e002`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e034`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14025e0ca`
- `ntoskrnl!CcUnpinData` at `0x14025d930`
- `ntoskrnl!CcUnpinData` at `0x14025daec`
- `ntoskrnl!CcUnpinData` at `0x14025e5d9`
- `ntoskrnl!CcUnpinData` at `0x1402b987c`
- `ntoskrnl!CcUnpinData` at `0x14025d930`
- `ntoskrnl!CcUnpinData` at `0x14025daec`
- `ntoskrnl!CcUnpinData` at `0x14025e5d9`
- `ntoskrnl!CcUnpinData` at `0x1402b987c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025d9da`
- `ntoskrnl!ExAcquireFastMutex` at `0x14025d9da`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025da00`
- `ntoskrnl!ExReleaseFastMutex` at `0x14025da00`
- `ntoskrnl!RtlCompareMemory` at `0x14025d8a9`
- `ntoskrnl!RtlCompareMemory` at `0x14025d8a9`
- `ntoskrnl!ExRaiseStatus` at `0x14025cd8e`
- `ntoskrnl!ExRaiseStatus` at `0x14025cd8e`
- `ntoskrnl!CcFlushCache` at `0x14025e421`
- `ntoskrnl!CcFlushCache` at `0x14025e421`

## string_xrefs

- `0x14025e62b`: `compressed`

## pseudocode

```c
void __fastcall TxfInitializeTopsStream(_DWORD *a1, __int64 a2, char a3)
{
  char v6; // r12
  __int64 v7; // r13
  __int64 v8; // r13
  unsigned int v9; // eax
  int v10; // edi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned __int8 v14; // di
  __int64 i; // rcx
  int v16; // eax
  __int64 v17; // rcx
  char v18; // al
  char v19; // al
  __int64 v20; // rdi
  __int16 v21; // dx
  _QWORD *v22; // r9
  __int16 v23; // ax
  __int64 v24; // rcx
  int v25; // r13d
  __int64 v26; // r12
  unsigned int v27; // eax
  __int64 v28; // rcx
  int v29; // edi
  __int64 v30; // r9
  _WORD *v31; // rcx
  char *v32; // rdx
  __int64 v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rcx
  __int64 *v36; // rdi
  void *v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // r9
  unsigned int v42; // eax
  __int64 v43; // rcx
  int v44; // edi
  __int64 v45; // rsi
  __int64 v46; // r9
  signed __int64 *v47; // r13
  size_t QuadPart; // rdi
  PVOID PoolWithTag; // rax
  _DWORD *v50; // rax
  void *v51; // rdx
  size_t v52; // r8
  PVOID v53; // rax
  int v54; // eax
  __int64 v55; // rdi
  int v56; // edx
  signed __int64 v57; // rcx
  signed __int64 v58; // rax
  int v59; // edx
  signed __int64 v60; // r8
  signed __int64 v61; // rdi
  __int64 v62; // rcx
  union _LARGE_INTEGER v63; // rax
  union _LARGE_INTEGER v64; // rdi
  unsigned __int64 v65; // rdi
  int v66; // edx
  signed __int64 v67; // rcx
  signed __int64 v68; // r8
  unsigned __int64 v69; // rax
  __int64 j; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  const char *v73; // rcx
  PLARGE_INTEGER Timeout; // [rsp+88h] [rbp-228h]
  int Timeouta; // [rsp+88h] [rbp-228h]
  size_t Size; // [rsp+A0h] [rbp-210h]
  size_t Sizea; // [rsp+A0h] [rbp-210h]
  char v78; // [rsp+D8h] [rbp-1D8h]
  char v79; // [rsp+D9h] [rbp-1D7h]
  __int64 v80; // [rsp+E0h] [rbp-1D0h] BYREF
  char v81; // [rsp+E8h] [rbp-1C8h]
  void *v82; // [rsp+F0h] [rbp-1C0h] BYREF
  char v83; // [rsp+F8h] [rbp-1B8h]
  PVOID Bcb; // [rsp+100h] [rbp-1B0h] BYREF
  union _LARGE_INTEGER EndOffset; // [rsp+108h] [rbp-1A8h] BYREF
  unsigned __int64 v86; // [rsp+110h] [rbp-1A0h]
  int v87; // [rsp+118h] [rbp-198h]
  int v88; // [rsp+11Ch] [rbp-194h] BYREF
  union _LARGE_INTEGER StartOffset; // [rsp+120h] [rbp-190h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+128h] [rbp-188h] BYREF
  UNICODE_STRING v91; // [rsp+130h] [rbp-180h] BYREF
  size_t v92; // [rsp+140h] [rbp-170h]
  _DWORD *v93; // [rsp+148h] [rbp-168h]
  __int64 v94[12]; // [rsp+158h] [rbp-158h] BYREF
  _DWORD *v95; // [rsp+1B8h] [rbp-F8h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+1C0h] [rbp-F0h] BYREF
  __int16 v97; // [rsp+1D0h] [rbp-E0h]
  __int16 v98; // [rsp+1D2h] [rbp-DEh]
  _QWORD *v99; // [rsp+1D8h] [rbp-D8h]
  UNICODE_STRING v100; // [rsp+1E0h] [rbp-D0h] BYREF
  __int128 Source1; // [rsp+1F0h] [rbp-C0h] BYREF
  __int64 v102[14]; // [rsp+208h] [rbp-A8h] BYREF

  v83 = a3;
  v93 = a1;
  v86 = a2 + 280;
  v80 = 0;
  *(_QWORD *)&v91.Length = 393220;
  v91.Buffer = L"$T";
  Bcb = 0;
  v6 = 0;
  v81 = 0;
  v100 = 0;
  v88 = 0;
  v82 = 0;
  FileOffset.QuadPart = 0;
  StartOffset.QuadPart = 0;
  IoStatus = 0;
  memset(v94, 0, 0x58u);
  v7 = *(_QWORD *)(a2 + 16);
  if ( a2 == *(_QWORD *)(v7 + 6248) )
  {
    v8 = *(_QWORD *)(v7 + 6240);
    if ( !v8 )
      ExRaiseStatus(-1073741608);
  }
  else
  {
    v8 = *(_QWORD *)(a2 + 96);
  }
  NtfsAcquireExclusiveScbEx((__int64)a1, v8, 0);
  v9 = TxfFlushAndInvalidateExistingStructures((int)a1, (__int64)&v80);
  v10 = v9;
  if ( v9 )
  {
    if ( NtfsStatusDebugFlags
      && (((v9 - 294) & 0xFFFFFFFA) != 0 || v9 == 295)
      && v9 < 0xFFFFFFED
      && v9 != -1073741608
      && v9 != -1073741802
      && v9 != -1073741807
      && v9 + 2147483643 > 1
      && v9 != 259 )
    {
      NtfsStatusTraceAndDebugInternal((__int64)a1, v9, 0x33048Au);
    }
    NtfsRaiseStatusInternal((__int64)a1, v10, 0, *(_QWORD *)(v8 + 184), 3343498);
  }
  if ( v80 )
  {
    NtfsReleaseFcbEx((__int64)a1, v80, 0);
    v80 = 0;
  }
  v11 = NtfsInitializeFileInDirectory((__int64)a1, v8, 0, (unsigned __int16 *)&NtfsTopsName, 0, 0, 0, 1, 0, 0);
  v80 = v11;
  if ( v11 )
  {
    v14 = 0;
    v78 = 0;
  }
  else
  {
    if ( (a1[109] & 0x2000) != 0 )
    {
      if ( (a1[4] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v12,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1215,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x3304C7u);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, *(_QWORD *)(v8 + 184), 3343559);
    }
    if ( !a3 )
    {
      if ( (a1[4] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v12,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1234,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x3304DAu);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, *(_QWORD *)(v8 + 184), 3343578);
    }
    v14 = 1;
    v78 = 1;
    v11 = NtfsInitializeFileInDirectory((__int64)a1, v8, 0, (unsigned __int16 *)&NtfsTopsName, 0, 0, 0, 1, 1, 0);
    v80 = v11;
  }
  if ( *(_QWORD *)(v11 + 112) )
  {
    v81 = 1;
  }
  else
  {
    NtfsAddPagingIoToFcb((__int64)a1, v80, 1);
    v81 = 1;
    if ( a1 )
    {
      v87 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v87 = i;
        if ( (unsigned int)i >= 2 )
          break;
        if ( *(_QWORD *)&a1[2 * i + 12] == v80 )
          *(_QWORD *)&a1[2 * i + 12] = 0;
      }
    }
  }
  v16 = *(_DWORD *)(v80 + 176);
  if ( (v16 & 0x4000) != 0 || (v16 & 0x800) != 0 )
  {
    if ( (!a1 || (a1[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
    {
      v73 = "encrypted";
      if ( (v16 & 0x4000) == 0 )
        v73 = "compressed";
      McTemplateU0spjs_EtwWriteTransfer((__int64)v73, v16 & 0x4000, v13, a2, a2 + 672, v73);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x330514u);
    NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, *(_QWORD *)(v8 + 184), 3343636);
  }
  *(_DWORD *)(v80 + 4) |= 0xA0000u;
  if ( *(_QWORD *)(v80 + 120) )
    NtfsClearPerFileQuota((__int64)a1, v80);
  if ( !v14 )
  {
    if ( !NtfsLookupInFileRecord((__int64)a1, v80, (_DWORD *)(v80 + 8), 0, 0, 0, 0, 0, 0, (__int64)v94) )
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v17,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1390,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x330576u);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3343734);
    }
    if ( *(_DWORD *)v94[0] != 16 )
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v17,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1377,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x330569u);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3343721);
    }
    if ( (*(_BYTE *)(v94[1] + 22) & 0xA) != 0 )
    {
      v6 = 1;
    }
    else
    {
      if ( v94[5] )
      {
        LODWORD(Size) = 0;
        v18 = NtfsLookupExternalAttribute((__int64)a1, v80, 0x30u, 0, 0, 0, 0, Size, (unsigned __int64)v94);
      }
      else
      {
        v18 = NtfsLookupInFileRecord((__int64)a1, v80, 0, 48, 0, 0, 0, 0, 0, (__int64)v94);
      }
      if ( v18 )
      {
        while ( 1 )
        {
          if ( v94[5] )
          {
            LODWORD(Sizea) = 0;
            v19 = NtfsLookupExternalAttribute((__int64)a1, v80, 0, 0, 0, 0, 0, Sizea, (unsigned __int64)v94);
          }
          else
          {
            v19 = NtfsLookupInFileRecord((__int64)a1, v80, 0, 0, 0, 0, 0, 0, 0, (__int64)v94);
          }
          if ( !v19 )
            break;
          v20 = v94[0];
          v21 = *(unsigned __int8 *)(v94[0] + 9);
          v17 = *(unsigned __int8 *)(v94[0] + 9);
          LOWORD(v17) = 2 * v17;
          v97 = v17;
          v98 = v17;
          v22 = (_QWORD *)(v94[0] + *(unsigned __int16 *)(v94[0] + 10));
          v99 = v22;
          if ( *(_DWORD *)v94[0] != 256 || (_WORD)v17 != 18 )
            goto LABEL_296;
          v17 = *v22 - 0x46005800540024LL;
          if ( *v22 == 0x46005800540024LL )
          {
            v17 = v22[1] - 0x5400410044005FLL;
            if ( v22[1] == 0x5400410044005FLL )
              v17 = *((unsigned __int16 *)v22 + 8) - 65LL;
          }
          if ( !v17 )
          {
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
          else
          {
LABEL_296:
            if ( *(_DWORD *)v94[0] != 128
              || (_BYTE)v21 && (v21 != v91.Length >> 1 || memcmp(v22, v91.Buffer, v91.Length))
              || (v23 = *(_WORD *)(v20 + 12), v17 = 16639, (v23 & 0x40FF) != 0)
              || (!*(_BYTE *)(v20 + 8) || !*(_QWORD *)(v20 + 16)) && (v17 = 49407, (v23 & 0xC0FF) != 0) )
            {
              v6 = 1;
              break;
            }
          }
        }
        v14 = v78;
      }
      else
      {
        v6 = 1;
      }
    }
    NtfsCleanupAttributeContext(v17, v94);
    if ( v6 )
    {
      v24 = v80;
      *(_DWORD *)(v80 + 4) &= ~0x20000u;
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v24,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1534,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x330606u);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3343878);
    }
  }
  memset(v94, 0, 0x58u);
  v100.Length = 0;
  v25 = 2 * (v14 ^ 1);
  v26 = a2 + 288;
  v27 = NtOfsCreateAttributeEx((__int64)a1, v80, &v100, 0x80u, v25, 1, (__int64 *)(a2 + 288));
  v29 = v27;
  if ( v27 )
  {
    if ( !v78 && v27 == -1073741772 )
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v28,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1589,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x33063Du);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3343933);
    }
    if ( NtfsStatusDebugFlags
      && (((v27 - 294) & 0xFFFFFFFA) != 0 || v27 == 295)
      && v27 < 0xFFFFFFED
      && v27 != -1073741608
      && v27 != -1073741802
      && v27 != -1073741807
      && v27 + 2147483643 > 1
      && v27 != 259 )
    {
      NtfsStatusTraceAndDebugInternal((__int64)a1, v27, 0x330642u);
    }
    NtfsRaiseStatusInternal((__int64)a1, v29, 0, v80, 3343938);
  }
  if ( !NtfsLookupInFileRecord(
          (__int64)a1,
          *(_QWORD *)(*(_QWORD *)v26 + 184LL),
          (_DWORD *)(*(_QWORD *)(*(_QWORD *)v26 + 184LL) + 8LL),
          *(_DWORD *)(*(_QWORD *)v26 + 256LL),
          (const UNICODE_STRING *)(*(_QWORD *)v26 + 264LL),
          0,
          0,
          0,
          0,
          (__int64)v94)
    && (*(_DWORD *)(*(_QWORD *)v26 + 512LL) & 4) == 0 )
  {
    NtfsAttachCorruption_BadOrOrphanFRS(
      (__int64)a1,
      2,
      3343948,
      v30,
      (_DWORD *)(*(_QWORD *)(*(_QWORD *)v26 + 184LL) + 8LL),
      *(_QWORD *)(*(_QWORD *)v26 + 184LL),
      0);
    NtfsAttachRepairInfoPriv((__int64)a1, 512, 0, (struct _LIST_ENTRY *)0xA90033064CLL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000102, 0x33064Cu);
    NtfsRaiseStatusInternal(
      (__int64)a1,
      -1073741566,
      *(_QWORD *)(*(_QWORD *)(v86 + 8) + 184LL) + 8,
      *(_QWORD *)(*(_QWORD *)(v86 + 8) + 184LL),
      3343948);
  }
  NtfsMapAttributeValue((__int64)a1, v80, &v82, &v88, &Bcb, (union _LARGE_INTEGER)v94);
  if ( v78 )
  {
    memset(v102, 0, 0x64u);
    v37 = v102;
    v82 = v102;
    if ( v94[2] )
    {
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
        v37 = v82;
      }
    }
    else
    {
      v94[2] = (__int64)Bcb;
      Bcb = 0;
    }
    memset(v37, 0, 0x64u);
    *(_WORD *)v82 = 10;
    *((_WORD *)v82 + 1) = 100;
    *((_DWORD *)v82 + 20) = -1;
    *((_DWORD *)v82 + 21) = -1;
    *((_DWORD *)v82 + 22) = -1;
    *((_WORD *)v82 + 48) = -1;
    *((_WORD *)v82 + 49) = -1;
    if ( a2 != *(_QWORD *)(*(_QWORD *)(a2 + 16) + 6248LL) )
    {
      ++*(_DWORD *)(a2 + 584);
      TxfUpdateTxfDataAttributeMembers(
        (__int64)a1,
        *(_QWORD *)(*(_QWORD *)(a2 + 96) + 184LL),
        v38,
        v39,
        (int)Timeout,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        (int *)(a2 + 584));
      NtfsAcquireExclusiveScbEx((__int64)a1, *(_QWORD *)(a2 + 80), 0);
      TxfUpdateTxfDataAttributeMembers(
        (__int64)a1,
        *(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL),
        v40,
        v41,
        Timeouta,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        (int *)(a2 + 584));
    }
    *((_DWORD *)v82 + 1) = *(_DWORD *)(a2 + 584);
    *((CLFS_LSN *)v82 + 4) = CLFS_LSN_INVALID_EXT;
    *(CLFS_LSN *)(a2 + 408) = CLFS_LSN_INVALID_EXT;
    LODWORD(Timeout) = *((unsigned __int16 *)v82 + 1);
    NtfsChangeAttributeValue((__int64)a1, v80, 0, v82, (SIZE_T)Timeout, 1, 1, 0, 0, v94);
    v36 = (__int64 *)(a2 + 280);
    ClearFlagInterlocked((unsigned int *)(*(_QWORD *)(a2 + 288) + 200LL), 544);
    NtfsUpdateScbFromAttribute((__int64)a1, *(_QWORD *)(a2 + 288), v94[0]);
  }
  else
  {
    v31 = v82;
    v32 = (char *)v82 + 8;
    *(_OWORD *)(a2 + 672) = *(_OWORD *)((char *)v82 + 8);
    if ( v83 )
    {
      Source1 = 0;
      if ( RtlCompareMemory(&Source1, v32, 0x10u) != 16 )
      {
        if ( (!a1 || (a1[4] & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        {
          McTemplateU0spj_EtwWriteTransfer(
            v33,
            (const EVENT_DESCRIPTOR *)txftxfdir_c1691,
            "TxfInitializeTopsStream",
            a2,
            a2 + 672);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x3306A3u);
        NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3344035);
      }
    }
    else
    {
      if ( v88 != 100 )
      {
        if ( (!a1 || (a1[4] & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        {
          McTemplateU0spj_EtwWriteTransfer(
            (__int64)v31,
            (const EVENT_DESCRIPTOR *)txftxfdir_c1666,
            "TxfInitializeTopsStream",
            a2,
            a2 + 672);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x33068Au);
        NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3344010);
      }
      if ( *v31 != 10 || v31[1] != 100 )
      {
        if ( (!a1 || (a1[4] & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        {
          McTemplateU0spj_EtwWriteTransfer(
            (__int64)v31,
            (const EVENT_DESCRIPTOR *)txftxfdir_c1651,
            "TxfInitializeTopsStream",
            a2,
            a2 + 672);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x33067Bu);
        NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3343995);
      }
    }
    if ( Bcb )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
    }
    v34 = v82;
    *(_QWORD *)(a2 + 408) = *((_QWORD *)v82 + 4);
    *(_DWORD *)(a2 + 128) |= 2u;
    *(_QWORD *)(a2 + 432) = v34[6];
    KeWaitForSingleObject(*(PVOID *)(a2 + 544), Executive, 0, 0, 0);
    *(_QWORD *)(a2 + 536) = *((_QWORD *)v82 + 7);
    KeReleaseMutex(*(PRKMUTEX *)(a2 + 544), 0);
    *(_QWORD *)(a2 + 440) = *((_QWORD *)v82 + 7);
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 24) + 472LL));
    *(_QWORD *)(a2 + 688) = *((_QWORD *)v82 + 5);
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 24) + 472LL));
    v35 = *(unsigned int *)(a2 + 584);
    if ( *((_DWORD *)v82 + 1) != (_DWORD)v35 )
    {
      if ( (!a1 || (a1[4] & 0x100000LL) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v35,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1764,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x3306ECu);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3344108);
    }
    v36 = (__int64 *)(a2 + 280);
  }
  v79 = 0;
  NtfsCleanupAttributeContext(v35, v94);
  memset(v94, 0, 0x58u);
  v42 = NtOfsCreateAttributeEx((__int64)a1, v80, &v91, 0x80u, v25, 1, v36);
  v44 = v42;
  if ( v42 )
  {
    if ( !v78 && v42 == -1073741772 )
    {
      if ( (!a1 || (a1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spj_EtwWriteTransfer(
          v43,
          (const EVENT_DESCRIPTOR *)txftxfdir_c1905,
          "TxfInitializeTopsStream",
          a2,
          a2 + 672);
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0190006, 0x330779u);
      NtfsRaiseStatusInternal((__int64)a1, -1072103418, 0, v80, 3344249);
    }
    if ( NtfsStatusDebugFlags
      && (((v42 - 294) & 0xFFFFFFFA) != 0 || v42 == 295)
      && v42 < 0xFFFFFFED
      && v42 != -1073741608
      && v42 != -1073741802
      && v42 != -1073741807
      && v42 + 2147483643 > 1
      && v42 != 259 )
    {
      NtfsStatusTraceAndDebugInternal((__int64)a1, v42, 0x33077Eu);
    }
    NtfsRaiseStatusInternal((__int64)a1, v44, 0, v80, 3344254);
  }
  v45 = *(_QWORD *)(a2 + 280);
  if ( (*(_DWORD *)(v45 + 200) & 0x20) == 0 )
    NtfsUpdateScbFromAttribute((__int64)a1, *(_QWORD *)(a2 + 280), 0);
  if ( (*(_DWORD *)(v45 + 200) & 8) != 0 )
  {
    v79 = 1;
    if ( !NtfsLookupInFileRecord(
            (__int64)a1,
            *(_QWORD *)(v45 + 184),
            (_DWORD *)(*(_QWORD *)(v45 + 184) + 8LL),
            *(_DWORD *)(v45 + 256),
            (const UNICODE_STRING *)(v45 + 264),
            0,
            0,
            0,
            0,
            (__int64)v94)
      && (*(_DWORD *)(v45 + 512) & 4) == 0 )
    {
      NtfsAttachCorruption_BadOrOrphanFRS(
        (__int64)a1,
        2,
        3344283,
        v46,
        (_DWORD *)(*(_QWORD *)(v45 + 184) + 8LL),
        *(_QWORD *)(v45 + 184),
        0);
      NtfsAttachRepairInfoPriv((__int64)a1, 512, 0, (struct _LIST_ENTRY *)0xA90033079BLL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000102, 0x33079Bu);
      NtfsRaiseStatusInternal((__int64)a1, -1073741566, *(_QWORD *)(v45 + 184) + 8, *(_QWORD *)(v45 + 184), 3344283);
    }
    NtfsConvertToNonresident((__int64)a1, v80, v94[0], 1, v94);
  }
  NtfsPreloadAllocationInternal((__int64)a1, v45, 0, 0, 0x7FFFFFFFFFFFFFFFLL, 0);
  v47 = (signed __int64 *)(v45 + 24);
  if ( *(__int64 *)(v45 + 24) < 0x100000 )
    NtfsAddAllocation((__int64)a1, 0, v45);
  v86 = ((*v47 + 4095) / 4096) & 0xFFFFFFF8LL;
  QuadPart = v86 >> 3;
  EndOffset.QuadPart = v86 >> 3;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v86 >> 3, 0x62547854u);
  *(_QWORD *)(a2 + 312) = PoolWithTag;
  memset(PoolWithTag, 0, QuadPart);
  v50 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), QuadPart, 0x62547854u);
  v51 = v50;
  *(_QWORD *)(a2 + 328) = v50;
  v95 = v50;
  v52 = QuadPart >> 2;
  v92 = QuadPart >> 2;
  if ( QuadPart >> 2 )
  {
    if ( ((unsigned __int8)v50 & 4) != 0 )
    {
      *v50 = -1;
      v92 = --v52;
      if ( !v52 )
        goto LABEL_214;
      v51 = v50 + 1;
      v95 = v50 + 1;
    }
    memset(v51, 0xFFu, 8 * (v52 >> 1));
    if ( (v52 & 1) != 0 )
      *((_DWORD *)v51 + v52 - 1) = -1;
    QuadPart = EndOffset.QuadPart;
  }
LABEL_214:
  v53 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), QuadPart, 0x62547854u);
  *(_QWORD *)(a2 + 344) = v53;
  memset(v53, 0, QuadPart);
  v54 = v86;
  v55 = a2 + 280;
  *(_DWORD *)(a2 + 304) = v86;
  *(_DWORD *)(a2 + 320) = v54;
  *(_DWORD *)(a2 + 336) = v54;
  *(_DWORD *)(a2 + 300) = v54;
  *(_DWORD *)(a2 + 296) = 0;
  *(_WORD *)(a2 + 352) = -1;
  NtfsCreateInternalAttributeStream((__int64)a1, v45, 0, 8, 0, 0);
  CcSetAdditionalCacheAttributes(*(PFILE_OBJECT *)(v45 + 280), 0, 1u);
  v56 = *(_DWORD *)(v45 + 200);
  if ( (v56 & 0x20000) != 0 )
  {
    v57 = *v47;
    if ( *(_QWORD *)(v45 + 32) < *v47 )
    {
      if ( v57 >= *(_QWORD *)(v45 + 464) )
        v57 = *(_QWORD *)(v45 + 464);
      v58 = *(_QWORD *)(v45 + 40);
      if ( v57 > v58 )
      {
        if ( (v56 & 0x200) != 0 )
          v58 = *(_QWORD *)(v45 + 40);
        v59 = *(_DWORD *)(v45 + 200);
        if ( (v59 & 0x20000) == 0 )
          goto LABEL_229;
        v60 = *(_QWORD *)(v45 + 464);
        if ( v60 >= v57 )
        {
          if ( v58 <= v57 )
          {
LABEL_229:
            *(_QWORD *)(v45 + 40) = v57;
            goto LABEL_231;
          }
          if ( *(_QWORD *)(*(_QWORD *)(v45 + 288) + 16LL) && v57 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v61 = (v57 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v61 < v60 )
              *(_QWORD *)(v45 + 464) = v61;
            v55 = a2 + 280;
            goto LABEL_229;
          }
        }
        *(_QWORD *)(v45 + 464) = v57;
        goto LABEL_229;
      }
    }
  }
LABEL_231:
  *(_QWORD *)(v45 + 32) = *v47;
  NtfsWriteFileSizes((__int64)a1, v45, 0, 1, 1, 1);
  NtfsCheckpointCurrentTransaction((__int64)a1);
  if ( v78 )
    NtfsSetCcFileSizes(
      *(struct _FILE_OBJECT **)(*(_QWORD *)(v55 + 8) + 280LL),
      *(_QWORD *)(v55 + 8),
      (struct _CC_FILE_SIZES *)(*(_QWORD *)(v55 + 8) + 24LL));
  NtfsSetCcFileSizes(*(struct _FILE_OBJECT **)(v45 + 280), v45, (struct _CC_FILE_SIZES *)(v45 + 24));
  v63 = *(union _LARGE_INTEGER *)(v45 + 40);
  if ( v63.QuadPart != *(_QWORD *)(v45 + 32) )
  {
    FileOffset = *(union _LARGE_INTEGER *)(v45 + 40);
    v64.QuadPart = *(_QWORD *)(v45 + 32) - 1LL;
    v86 = v64.QuadPart;
    StartOffset = v63;
    while ( v63.QuadPart <= v64.QuadPart )
    {
      EndOffset.QuadPart = v63.QuadPart + 4095;
      if ( v63.QuadPart + 4095 > v64.QuadPart )
        EndOffset = v64;
      CcZeroData(*(PFILE_OBJECT *)(v45 + 280), &StartOffset, &EndOffset, 1u);
      v63.QuadPart = EndOffset.QuadPart + 1;
      StartOffset.QuadPart = EndOffset.QuadPart + 1;
    }
    v65 = v64.QuadPart + 1;
    v86 = v65;
    FsRtlAcquireHeaderMutex(v45 + 120, v45 + 160);
    v66 = *(_DWORD *)(v45 + 200);
    if ( (v66 & 0x20000) == 0 )
      goto LABEL_248;
    v67 = *(_QWORD *)(v45 + 32);
    v68 = *(_QWORD *)(v45 + 464);
    if ( v68 >= v67 )
    {
      if ( *(_QWORD *)(v45 + 40) <= v67 )
        goto LABEL_248;
      if ( *(_QWORD *)(*(_QWORD *)(v45 + 288) + 16LL) && v67 != 0x7FFFFFFFFFFFFFFFLL )
      {
        if ( (__int64)((v67 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v68 )
        {
          v69 = (*(_QWORD *)(v45 + 32) + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
LABEL_247:
          *(_QWORD *)(v45 + 464) = v69;
        }
LABEL_248:
        *(_QWORD *)(v45 + 40) = *(_QWORD *)(v45 + 32);
        FsRtlReleaseHeaderMutex(v45 + 120, v45 + 160);
        CcFlushCache(
          (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v45 + 288) + 16LL),
          &FileOffset,
          v65 - FileOffset.LowPart,
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
            NtfsStatusTraceAndDebugInternal((__int64)a1, IoStatus.Status, 0x330860u);
          }
          NtfsRaiseStatusInternal(
            (__int64)a1,
            IoStatus.Status,
            *(_QWORD *)(v45 + 184) + 8,
            *(_QWORD *)(v45 + 184),
            3344480);
        }
        NtfsWriteFileSizes((__int64)a1, v45, 0, 1, 1, 1);
        NtfsCheckpointCurrentTransaction((__int64)a1);
        goto LABEL_259;
      }
    }
    v69 = *(_QWORD *)(v45 + 32);
    goto LABEL_247;
  }
LABEL_259:
  if ( *(_QWORD *)(v80 + 320) != a2 )
  {
    if ( a2 )
    {
      _InterlockedAdd((volatile signed __int32 *)(a2 + 64), 1u);
      _InterlockedAdd((volatile signed __int32 *)(a2 + 36), 1u);
    }
    v62 = *(_QWORD *)(v80 + 320);
    if ( v62 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v62 + 36));
      v62 = *(_QWORD *)(v80 + 320);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v62 + 64), 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb(*(char **)(v80 + 320));
    }
    *(_QWORD *)(v80 + 320) = a2;
  }
  if ( v81 )
  {
    if ( a1 && a1[7] )
    {
      for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
      {
        v62 = (unsigned int)j;
        v71 = *(_QWORD *)&a1[2 * j + 12];
        if ( !v71 || v71 == v80 )
        {
          *(_QWORD *)&a1[2 * (unsigned int)j + 12] = v80;
          break;
        }
      }
    }
    else
    {
      NtfsReleasePagingResourcePriv(v62, v80);
      if ( a1 )
      {
        v72 = 0;
        v62 = v80;
        do
        {
          if ( *(_QWORD *)&a1[2 * v72 + 12] == v62 )
            *(_QWORD *)&a1[2 * v72 + 12] = 0;
          ++v72;
        }
        while ( v72 != 2 );
      }
    }
  }
  if ( v79 )
    NtfsCleanupAttributeContext(v62, v94);
  if ( Bcb )
    CcUnpinData(Bcb);
}

```

## disassembly

```asm
0x14025cc9c  mov     r11, rsp
0x14025cc9f  mov     [r11+18h], rbx
0x14025cca3  mov     [r11+20h], rsi
0x14025cca7  push    rdi
0x14025cca8  push    r12
0x14025ccaa  push    r13
0x14025ccac  push    r14
0x14025ccae  push    r15
0x14025ccb0  sub     rsp, 220h
0x14025ccb7  mov     rax, cs:__security_cookie
0x14025ccbe  xor     rax, rsp
0x14025ccc1  mov     [rsp+248h+var_38], rax
0x14025ccc9  mov     sil, r8b
0x14025cccc  mov     [rsp+248h+var_1B8], r8b
0x14025ccd4  mov     r14, rdx
0x14025ccd7  mov     rbx, rcx
0x14025ccda  mov     [rsp+248h+var_168], rcx
0x14025cce2  lea     rax, [rdx+118h]
0x14025cce9  mov     [rsp+248h+var_1A0], rax
0x14025ccf1  xor     r15d, r15d
0x14025ccf4  mov     [rsp+248h+var_1D0], r15
0x14025ccf9  mov     qword ptr [r11-180h], 60004h
0x14025cd04  lea     rax, aT; "$T"
0x14025cd0b  mov     [r11-178h], rax
0x14025cd12  mov     [r11-1B0h], r15
0x14025cd19  mov     r12b, r15b
0x14025cd1c  mov     [r11-1C8h], r15b
0x14025cd23  xorps   xmm0, xmm0
0x14025cd26  movups  [rsp+248h+var_D0], xmm0
0x14025cd2e  mov     [r11-194h], r15d
0x14025cd35  mov     [r11-1C0h], r15
0x14025cd3c  mov     [r11-188h], r15
0x14025cd43  mov     [r11-190h], r15
0x14025cd4a  movups  xmmword ptr [rsp+248h+IoStatus], xmm0
0x14025cd52  mov     [rsp+248h+var_1D7], r15b
0x14025cd57  xor     edx, edx; Val
0x14025cd59  lea     r8d, [r15+58h]; Size
0x14025cd5d  lea     rcx, [r11-158h]; void *
0x14025cd64  call    memset
0x14025cd69  nop
0x14025cd6a  mov     r13, [r14+10h]
0x14025cd6e  cmp     r14, [r13+1868h]
0x14025cd75  jnz     short loc_14025CD9A
0x14025cd77  mov     r13, [r13+1860h]
0x14025cd7e  test    r13, r13
0x14025cd81  jnz     short loc_14025CD9E
0x14025cd83  mov     al, cs:NtfsStatusDebugFlags
0x14025cd89  mov     ecx, 0C00000D8h; Status
0x14025cd8e  call    cs:__imp_ExRaiseStatus
0x14025cd9a  mov     r13, [r14+60h]
0x14025cd9e  xor     r8d, r8d
0x14025cda1  mov     rdx, r13
0x14025cda4  mov     rcx, rbx
0x14025cda7  call    NtfsAcquireExclusiveScbEx
0x14025cdac  lea     rax, [rsp+248h+var_1D0]
0x14025cdb1  mov     [rsp+248h+Timeout], rax; __int64
0x14025cdb6  xor     r9d, r9d
0x14025cdb9  lea     r8, NtfsTopsName
0x14025cdc0  mov     rdx, r13
0x14025cdc3  mov     rcx, rbx; int
0x14025cdc6  call    TxfFlushAndInvalidateExistingStructures
0x14025cdcb  mov     edi, eax
0x14025cdcd  test    eax, eax
0x14025cdcf  jz      loc_14025CE56
0x14025cdd5  mov     cl, cs:NtfsStatusDebugFlags
0x14025cddb  test    cl, cl
0x14025cddd  jz      short loc_14025CE39
0x14025cddf  lea     ecx, [rax-126h]
0x14025cde5  test    ecx, 0FFFFFFFAh
0x14025cdeb  jnz     short loc_14025CDF4
0x14025cded  cmp     eax, 127h
0x14025cdf2  jnz     short loc_14025CE39
0x14025cdf4  cmp     edi, 0FFFFFFEDh
0x14025cdf7  jnb     short loc_14025CE39
0x14025cdf9  cmp     edi, 0C00000D8h
0x14025cdff  jz      short loc_14025CE39
0x14025ce01  cmp     edi, 0C0000016h
0x14025ce07  jz      short loc_14025CE39
0x14025ce09  cmp     edi, 0C0000011h
0x14025ce0f  jz      short loc_14025CE39
0x14025ce11  add     eax, 7FFFFFFBh
0x14025ce16  mov     r15d, 1
0x14025ce1c  cmp     eax, r15d
0x14025ce1f  jbe     short loc_14025CE39
0x14025ce21  cmp     edi, 103h
0x14025ce27  jz      short loc_14025CE39
0x14025ce29  mov     r8d, 33048Ah
0x14025ce2f  mov     edx, edi
0x14025ce31  mov     rcx, rbx
0x14025ce34  call    NtfsStatusTraceAndDebugInternal
0x14025ce39  mov     [rsp+248h+Timeout], 33048Ah
0x14025ce42  mov     r9, [r13+0B8h]
0x14025ce49  xor     r8d, r8d
0x14025ce4c  mov     edx, edi
0x14025ce4e  mov     rcx, rbx
0x14025ce51  call    NtfsRaiseStatusInternal
0x14025ce56  mov     rdx, [rsp+248h+var_1D0]
0x14025ce5b  test    rdx, rdx
0x14025ce5e  jz      short loc_14025CE70
0x14025ce60  xor     r8d, r8d
0x14025ce63  mov     rcx, rbx
0x14025ce66  call    NtfsReleaseFcbEx
0x14025ce6b  mov     [rsp+248h+var_1D0], r15
0x14025ce70  mov     dword ptr [rsp+248h+var_200], r15d; int
0x14025ce75  mov     dword ptr [rsp+248h+var_208], r15d; int
0x14025ce7a  mov     r15d, 1
0x14025ce80  mov     byte ptr [rsp+248h+Size], r15b; char
0x14025ce85  xor     eax, eax
0x14025ce87  mov     byte ptr [rsp+248h+var_218], al; char
0x14025ce8b  mov     [rsp+248h+IgnoreCase], al; char
0x14025ce8f  mov     byte ptr [rsp+248h+Timeout], al; char
0x14025ce93  lea     r9, NtfsTopsName
0x14025ce9a  xor     r8d, r8d
0x14025ce9d  mov     rdx, r13
0x14025cea0  mov     rcx, rbx; int
0x14025cea3  call    NtfsInitializeFileInDirectory
0x14025cea8  mov     [rsp+248h+var_1D0], rax
0x14025cead  test    rax, rax
0x14025ceb0  jnz     loc_14025CFEE
0x14025ceb6  test    dword ptr [rbx+1B4h], 2000h
0x14025cec0  jz      short loc_14025CF33
0x14025cec2  mov     eax, [rbx+10h]
0x14025cec5  bt      rax, 14h
0x14025ceca  jb      short loc_14025CEF7
0x14025cecc  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 8
0x14025ced3  jz      short loc_14025CEF7
0x14025ced5  lea     rax, [r14+2A0h]
0x14025cedc  mov     [rsp+248h+Timeout], rax
0x14025cee1  mov     r9, r14
0x14025cee4  lea     r8, aTxfinitializet; "TxfInitializeTopsStream"
0x14025ceeb  lea     rdx, txftxfdir_c1215
0x14025cef2  call    McTemplateU0spj_EtwWriteTransfer
0x14025cef7  mov     al, cs:NtfsStatusDebugFlags
0x14025cefd  mov     esi, 0C0190006h
0x14025cf02  test    al, al
0x14025cf04  jz      short loc_14025CF16
0x14025cf06  mov     r8d, 3304C7h
0x14025cf0c  mov     edx, esi
0x14025cf0e  mov     rcx, rbx
0x14025cf11  call    NtfsStatusTraceAndDebugInternal
0x14025cf16  mov     [rsp+248h+Timeout], 3304C7h
0x14025cf1f  mov     r9, [r13+0B8h]
0x14025cf26  xor     r8d, r8d
0x14025cf29  mov     edx, esi
0x14025cf2b  mov     rcx, rbx
0x14025cf2e  call    NtfsRaiseStatusInternal
0x14025cf33  test    sil, sil
0x14025cf36  jnz     short loc_14025CFA9
0x14025cf38  mov     eax, [rbx+10h]
0x14025cf3b  bt      rax, 14h
0x14025cf40  jb      short loc_14025CF6D
0x14025cf42  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 8
0x14025cf49  jz      short loc_14025CF6D
0x14025cf4b  lea     rax, [r14+2A0h]
0x14025cf52  mov     [rsp+248h+Timeout], rax
0x14025cf57  mov     r9, r14
0x14025cf5a  lea     r8, aTxfinitializet; "TxfInitializeTopsStream"
0x14025cf61  lea     rdx, txftxfdir_c1234
0x14025cf68  call    McTemplateU0spj_EtwWriteTransfer
0x14025cf6d  mov     al, cs:NtfsStatusDebugFlags
0x14025cf73  mov     esi, 0C0190006h
0x14025cf78  test    al, al
0x14025cf7a  jz      short loc_14025CF8C
0x14025cf7c  mov     r8d, 3304DAh
0x14025cf82  mov     edx, esi
0x14025cf84  mov     rcx, rbx
0x14025cf87  call    NtfsStatusTraceAndDebugInternal
0x14025cf8c  mov     [rsp+248h+Timeout], 3304DAh
0x14025cf95  mov     r9, [r13+0B8h]
0x14025cf9c  xor     r8d, r8d
0x14025cf9f  mov     edx, esi
0x14025cfa1  mov     rcx, rbx
0x14025cfa4  call    NtfsRaiseStatusInternal
0x14025cfa9  mov     dil, r15b
0x14025cfac  mov     [rsp+248h+var_1D8], r15b
0x14025cfb1  mov     dword ptr [rsp+248h+var_200], 0; int
0x14025cfb9  mov     dword ptr [rsp+248h+var_208], r15d; int
0x14025cfbe  mov     byte ptr [rsp+248h+Size], r15b; char
0x14025cfc3  mov     byte ptr [rsp+248h+var_218], 0; char
0x14025cfc8  mov     [rsp+248h+IgnoreCase], 0; char
0x14025cfcd  mov     byte ptr [rsp+248h+Timeout], 0; char
0x14025cfd2  lea     r9, NtfsTopsName
0x14025cfd9  xor     r8d, r8d
0x14025cfdc  mov     rdx, r13
0x14025cfdf  mov     rcx, rbx; int
0x14025cfe2  call    NtfsInitializeFileInDirectory
0x14025cfe7  mov     [rsp+248h+var_1D0], rax
0x14025cfec  jmp     short loc_14025CFF6
0x14025cfee  xor     dil, dil
0x14025cff1  mov     [rsp+248h+var_1D8], dil
0x14025cff6  cmp     qword ptr [rax+70h], 0
0x14025cffb  jnz     short loc_14025D04D
0x14025cffd  mov     r8b, r15b
0x14025d000  mov     rdx, [rsp+248h+var_1D0]
0x14025d005  mov     rcx, rbx
0x14025d008  call    NtfsAddPagingIoToFcb
0x14025d00d  mov     [rsp+248h+var_1C8], r15b
0x14025d015  test    rbx, rbx
0x14025d018  jz      short loc_14025D055
0x14025d01a  mov     [rsp+248h+var_198], 0
0x14025d025  xor     ecx, ecx
0x14025d027  mov     [rsp+248h+var_198], ecx
0x14025d02e  cmp     ecx, 2
0x14025d031  jnb     short loc_14025D055
0x14025d033  mov     rax, [rsp+248h+var_1D0]
0x14025d038  cmp     [rbx+rcx*8+30h], rax
0x14025d03d  jnz     short loc_14025D048
0x14025d03f  mov     qword ptr [rbx+rcx*8+30h], 0
0x14025d048  add     ecx, r15d
0x14025d04b  jmp     short loc_14025D027
0x14025d04d  mov     [rsp+248h+var_1C8], r15b
0x14025d055  mov     rcx, [rsp+248h+var_1D0]
0x14025d05a  mov     eax, [rcx+0B0h]
0x14025d060  mov     edx, eax
0x14025d062  and     edx, 4000h
0x14025d068  jnz     loc_14025E613
0x14025d06e  bt      eax, 0Bh
0x14025d072  jb      loc_14025E613
0x14025d078  mov     eax, [rcx+4]
0x14025d07b  or      eax, 0A0000h
0x14025d080  mov     [rcx+4], eax
0x14025d083  mov     eax, [rcx+4]
0x14025d086  mov     rdx, [rsp+248h+var_1D0]
0x14025d08b  xor     r13d, r13d
0x14025d08e  cmp     [rdx+78h], r13
0x14025d092  jz      short loc_14025D09F
0x14025d094  xor     r8d, r8d
0x14025d097  mov     rcx, rbx
0x14025d09a  call    NtfsClearPerFileQuota
0x14025d09f  test    dil, dil
0x14025d0a2  jnz     loc_14025D4DA
0x14025d0a8  mov     [rsp+248h+var_1D7], r15b
0x14025d0ad  mov     rdx, [rsp+248h+var_1D0]
0x14025d0b2  lea     r8, [rdx+8]
0x14025d0b6  lea     rax, [rsp+248h+var_158]
0x14025d0be  mov     [rsp+248h+var_200], rax
0x14025d0c3  mov     dword ptr [rsp+248h+var_208], r13d
0x14025d0c8  mov     [rsp+248h+Size], r13
0x14025d0cd  mov     byte ptr [rsp+248h+var_218], r13b
0x14025d0d2  mov     qword ptr [rsp+248h+IgnoreCase], r13
0x14025d0d7  mov     [rsp+248h+Timeout], r13
0x14025d0dc  xor     r9d, r9d
0x14025d0df  mov     rcx, rbx
0x14025d0e2  call    NtfsLookupInFileRecord
0x14025d0e7  test    al, al
0x14025d0e9  jz      loc_14025D466
0x14025d0ef  mov     rax, [rsp+248h+var_158]
0x14025d0f7  cmp     dword ptr [rax], 10h
0x14025d0fa  jz      short loc_14025D170
0x14025d0fc  test    rbx, rbx
0x14025d0ff  jz      short loc_14025D10B
0x14025d101  mov     eax, [rbx+10h]
0x14025d104  bt      rax, 14h
0x14025d109  jb      short loc_14025D136
0x14025d10b  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 8
0x14025d112  jz      short loc_14025D136
0x14025d114  lea     rax, [r14+2A0h]
0x14025d11b  mov     [rsp+248h+Timeout], rax
0x14025d120  mov     r9, r14
0x14025d123  lea     r8, aTxfinitializet; "TxfInitializeTopsStream"
0x14025d12a  lea     rdx, txftxfdir_c1377
0x14025d131  call    McTemplateU0spj_EtwWriteTransfer
0x14025d136  mov     al, cs:NtfsStatusDebugFlags
0x14025d13c  mov     esi, 0C0190006h
0x14025d141  test    al, al
0x14025d143  jz      short loc_14025D155
0x14025d145  mov     r8d, 330569h
0x14025d14b  mov     edx, esi
0x14025d14d  mov     rcx, rbx
0x14025d150  call    NtfsStatusTraceAndDebugInternal
0x14025d155  mov     [rsp+248h+Timeout], 330569h
0x14025d15e  mov     r9, [rsp+248h+var_1D0]
0x14025d163  xor     r8d, r8d
0x14025d166  mov     edx, esi
0x14025d168  mov     rcx, rbx
0x14025d16b  call    NtfsRaiseStatusInternal
0x14025d170  mov     rax, [rsp+248h+var_150]
0x14025d178  test    byte ptr [rax+16h], 0Ah
0x14025d17c  jnz     loc_14025D459
0x14025d182  lea     rax, [rsp+248h+var_158]
0x14025d18a  mov     rdx, [rsp+248h+var_1D0]; int
0x14025d18f  mov     rcx, rbx; int
0x14025d192  cmp     [rsp+248h+var_130], r13
0x14025d19a  jnz     short loc_14025D1CA
0x14025d19c  mov     [rsp+248h+var_200], rax
0x14025d1a1  mov     dword ptr [rsp+248h+var_208], r13d
0x14025d1a6  mov     [rsp+248h+Size], r13
0x14025d1ab  mov     byte ptr [rsp+248h+var_218], r13b
0x14025d1b0  mov     qword ptr [rsp+248h+IgnoreCase], r13
0x14025d1b5  mov     [rsp+248h+Timeout], r13
0x14025d1ba  mov     r9d, 30h ; '0'
0x14025d1c0  xor     r8d, r8d
0x14025d1c3  call    NtfsLookupInFileRecord
0x14025d1c8  jmp     short loc_14025D1EF
0x14025d1ca  mov     qword ptr [rsp+248h+var_208], rax; __int64
0x14025d1cf  mov     dword ptr [rsp+248h+Size], r13d; Size
0x14025d1d4  mov     [rsp+248h+var_218], r13; void *
0x14025d1d9  mov     [rsp+248h+IgnoreCase], r13b; IgnoreCase
0x14025d1de  mov     [rsp+248h+Timeout], r13; __int64
0x14025d1e3  xor     r9d, r9d; ConstantNameB
  ... truncated ...
```
