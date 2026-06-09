# TxfInitializeTopsStream

- ea: `0x14025cc9c`
- end: `0x14025e696`
- name: `TxfInitializeTopsStream`
- size: `6650`
- prototype: `__int64 __fastcall(int)`
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
  __int64 v62; // r9
  union _LARGE_INTEGER v63; // rax
  union _LARGE_INTEGER v64; // rdi
  unsigned __int64 v65; // rdi
  int v66; // edx
  signed __int64 v67; // rcx
  signed __int64 v68; // r8
  unsigned __int64 v69; // rax
  int v70; // r9d
  __int64 j; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  const char *v74; // rcx
  PLARGE_INTEGER Timeout; // [rsp+88h] [rbp-228h]
  int Timeouta; // [rsp+88h] [rbp-228h]
  int v77; // [rsp+98h] [rbp-218h]
  int v78; // [rsp+98h] [rbp-218h]
  int v79; // [rsp+98h] [rbp-218h]
  int v80; // [rsp+98h] [rbp-218h]
  size_t Size; // [rsp+A0h] [rbp-210h]
  char v82; // [rsp+D8h] [rbp-1D8h]
  char v83; // [rsp+D9h] [rbp-1D7h]
  __int64 v84; // [rsp+E0h] [rbp-1D0h] BYREF
  char v85; // [rsp+E8h] [rbp-1C8h]
  void *v86; // [rsp+F0h] [rbp-1C0h] BYREF
  char v87; // [rsp+F8h] [rbp-1B8h]
  PVOID Bcb; // [rsp+100h] [rbp-1B0h] BYREF
  union _LARGE_INTEGER EndOffset; // [rsp+108h] [rbp-1A8h] BYREF
  unsigned __int64 v90; // [rsp+110h] [rbp-1A0h]
  int v91; // [rsp+118h] [rbp-198h]
  int v92; // [rsp+11Ch] [rbp-194h] BYREF
  union _LARGE_INTEGER StartOffset; // [rsp+120h] [rbp-190h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+128h] [rbp-188h] BYREF
  __int64 v95; // [rsp+130h] [rbp-180h] BYREF
  void *Buf2; // [rsp+138h] [rbp-178h]
  size_t v97; // [rsp+140h] [rbp-170h]
  _DWORD *v98; // [rsp+148h] [rbp-168h]
  __int64 v99[12]; // [rsp+158h] [rbp-158h] BYREF
  _DWORD *v100; // [rsp+1B8h] [rbp-F8h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+1C0h] [rbp-F0h] BYREF
  __int16 v102; // [rsp+1D0h] [rbp-E0h]
  __int16 v103; // [rsp+1D2h] [rbp-DEh]
  _QWORD *v104; // [rsp+1D8h] [rbp-D8h]
  __int128 v105; // [rsp+1E0h] [rbp-D0h] BYREF
  __int128 Source1; // [rsp+1F0h] [rbp-C0h] BYREF
  __int64 v107[14]; // [rsp+208h] [rbp-A8h] BYREF

  v3 = a3;
  v87 = a3;
  v98 = a1;
  v90 = a2 + 280;
  v6 = 0;
  v84 = 0;
  v95 = 393220;
  Buf2 = L"$T";
  Bcb = 0;
  v7 = 0;
  v85 = 0;
  v105 = 0;
  v92 = 0;
  v86 = 0;
  FileOffset.QuadPart = 0;
  StartOffset.QuadPart = 0;
  IoStatus = 0;
  memset(v99, 0, 0x58u);
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
  v10 = TxfFlushAndInvalidateExistingStructures((int)a1, (__int64)&v84);
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
  if ( v84 )
  {
    NtfsReleaseFcbEx(a1, v84, 0);
    v84 = v6;
  }
  v12 = NtfsInitializeFileInDirectory((int)a1, 0, 0, 0, 1, v6, v6);
  v84 = v12;
  if ( v12 )
  {
    LOBYTE(v11) = 0;
    v82 = 0;
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
    v82 = 1;
    v12 = NtfsInitializeFileInDirectory((int)a1, 0, 0, 0, 1, 1, 0);
    v84 = v12;
  }
  if ( *(_QWORD *)(v12 + 112) )
  {
    v85 = 1;
  }
  else
  {
    LOBYTE(v14) = 1;
    NtfsAddPagingIoToFcb(a1, v84, v14);
    v85 = 1;
    if ( a1 )
    {
      v91 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v91 = i;
        if ( (unsigned int)i >= 2 )
          break;
        if ( *(_QWORD *)&a1[2 * i + 12] == v84 )
          *(_QWORD *)&a1[2 * i + 12] = 0;
      }
    }
  }
  v16 = *(_DWORD *)(v84 + 176);
  if ( (v16 & 0x4000) != 0 || (v16 & 0x800) != 0 )
  {
    if ( (!a1 || (a1[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
    {
      v74 = "encrypted";
      if ( (v16 & 0x4000) == 0 )
        v74 = "compressed";
      McTemplateU0spjs_EtwWriteTransfer((_DWORD)v74, v16 & 0x4000, v14, a2, a2 + 672, (__int64)v74);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3222863878LL, 3343636);
    NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, *(_QWORD *)(v9 + 184), 3343636);
    __debugbreak();
    JUMPOUT(0x14025E696LL);
  }
  *(_DWORD *)(v84 + 4) |= 0xA0000u;
  if ( *(_QWORD *)(v84 + 120) )
    NtfsClearPerFileQuota(a1, v84, 0);
  if ( !(_BYTE)v11 )
  {
    LOBYTE(v77) = 0;
    if ( (unsigned __int8)NtfsLookupInFileRecord(a1, v84, v84 + 8, 0, 0, 0, v77, 0, 0, v99) )
    {
      if ( *(_DWORD *)v99[0] != 16 )
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
        NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3343721);
      }
      if ( (*(_BYTE *)(v99[1] + 22) & 0xA) != 0 )
      {
        v7 = 1;
      }
      else
      {
        if ( v99[5] )
        {
          LODWORD(Size) = 0;
          v18 = NtfsLookupExternalAttribute((int)a1, v84, 48, 0, 0, 0, 0, Size, (__int64)v99);
        }
        else
        {
          LOBYTE(v78) = 0;
          v18 = NtfsLookupInFileRecord(a1, v84, 0, 48, 0, 0, v78, 0, 0, v99);
        }
        if ( v18 )
          goto LABEL_63;
        v7 = 1;
      }
      while ( 1 )
      {
        NtfsCleanupAttributeContext(v17, v99);
        if ( !v7 )
          break;
        v23 = v84;
        *(_DWORD *)(v84 + 4) &= ~0x20000u;
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
        v22 = NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3343878);
LABEL_91:
        if ( *(_BYTE *)(v11 + 8) && *(_QWORD *)(v11 + 16) || (v17 = 49407, (v22 & 0xC0FF) == 0) )
        {
LABEL_63:
          while ( 1 )
          {
            if ( v99[5] )
            {
              LODWORD(Size) = 0;
              v19 = NtfsLookupExternalAttribute((int)a1, v84, 0, 0, 0, 0, 0, Size, (__int64)v99);
            }
            else
            {
              LOBYTE(v78) = 0;
              v19 = NtfsLookupInFileRecord(a1, v84, 0, 0, 0, 0, v78, 0, 0, v99);
            }
            if ( !v19 )
              break;
            v11 = v99[0];
            v20 = *(unsigned __int8 *)(v99[0] + 9);
            v17 = *(unsigned __int8 *)(v99[0] + 9);
            LOWORD(v17) = 2 * v17;
            v102 = v17;
            v103 = v17;
            v21 = (_QWORD *)(v99[0] + *(unsigned __int16 *)(v99[0] + 10));
            v104 = v21;
            if ( *(_DWORD *)v99[0] != 256 || (_WORD)v17 != 18 )
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
              if ( *(_DWORD *)v99[0] == 128
                && (!(_BYTE)v20 || v20 == (unsigned __int16)v95 >> 1 && !memcmp(v21, Buf2, (unsigned __int16)v95)) )
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
        LOBYTE(v11) = v82;
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
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3343734);
    }
  }
  memset(v99, 0, 0x58u);
  LOWORD(v105) = 0;
  v24 = 2 * ((unsigned __int8)v11 ^ 1);
  v25 = a2 + 288;
  Attribute = NtOfsCreateAttributeEx((_DWORD)a1, v84, (unsigned int)&v105, 128, v24, 1, a2 + 288);
  v28 = Attribute;
  if ( Attribute )
  {
    if ( !v82 && Attribute == -1073741772 )
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
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3343933);
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
    NtfsRaiseStatusInternal((_DWORD)a1, v28, 0, v84, 3343938);
  }
  v29 = 0;
  LOBYTE(v79) = 0;
  if ( !(unsigned __int8)NtfsLookupInFileRecord(
                           a1,
                           *(_QWORD *)(*(_QWORD *)v25 + 184LL),
                           *(_QWORD *)(*(_QWORD *)v25 + 184LL) + 8LL,
                           *(unsigned int *)(*(_QWORD *)v25 + 256LL),
                           *(_QWORD *)v25 + 264LL,
                           0,
                           v79,
                           0,
                           0,
                           v99)
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
      *(_QWORD *)(*(_QWORD *)(v90 + 8) + 184LL) + 8,
      *(_QWORD *)(*(_QWORD *)(v90 + 8) + 184LL),
      3343948);
  }
  NtfsMapAttributeValue(a1, v84, &v86, &v92, &Bcb, v99);
  if ( v82 == (_BYTE)v29 )
  {
    v31 = v86;
    v32 = (char *)v86 + 8;
    *(_OWORD *)(a2 + 672) = *(_OWORD *)((char *)v86 + 8);
    if ( !v87 )
    {
      if ( v92 == 100 )
      {
        if ( *v31 == 10 && v31[1] == 100 )
        {
LABEL_157:
          if ( Bcb )
          {
            CcUnpinData(Bcb);
            Bcb = 0;
          }
          v34 = v86;
          *(_QWORD *)(a2 + 408) = *((_QWORD *)v86 + 4);
          *(_DWORD *)(a2 + 128) |= 2u;
          *(_QWORD *)(a2 + 432) = v34[6];
          KeWaitForSingleObject(*(PVOID *)(a2 + 544), Executive, 0, 0, 0);
          *(_QWORD *)(a2 + 536) = *((_QWORD *)v86 + 7);
          KeReleaseMutex(*(PRKMUTEX *)(a2 + 544), 0);
          *(_QWORD *)(a2 + 440) = *((_QWORD *)v86 + 7);
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 24) + 472LL));
          *(_QWORD *)(a2 + 688) = *((_QWORD *)v86 + 5);
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 24) + 472LL));
          v35 = *(unsigned int *)(a2 + 584);
          if ( *((_DWORD *)v86 + 1) != (_DWORD)v35 )
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
            NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3344108);
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
        NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3343995);
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
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3344010);
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
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3344035);
    }
    goto LABEL_157;
  }
  memset(v107, 0, 0x64u);
  v37 = v107;
  v86 = v107;
  if ( v99[2] == v29 )
  {
    v99[2] = (__int64)Bcb;
    Bcb = (PVOID)v29;
  }
  else if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = (PVOID)v29;
    v37 = v86;
  }
  memset(v37, 0, 0x64u);
  *(_WORD *)v86 = 10;
  *((_WORD *)v86 + 1) = 100;
  *((_DWORD *)v86 + 20) = -1;
  *((_DWORD *)v86 + 21) = -1;
  *((_DWORD *)v86 + 22) = -1;
  *((_WORD *)v86 + 48) = -1;
  *((_WORD *)v86 + 49) = -1;
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
  *((_DWORD *)v86 + 1) = *(_DWORD *)(a2 + 584);
  *((CLFS_LSN *)v86 + 4) = CLFS_LSN_INVALID_EXT;
  *(CLFS_LSN *)(a2 + 408) = CLFS_LSN_INVALID_EXT;
  LODWORD(Timeout) = *((unsigned __int16 *)v86 + 1);
  NtfsChangeAttributeValue((int)a1, v84, 0, (int)v86, (SIZE_T)Timeout, 1, 1, v29, v29, v99);
  v36 = a2 + 280;
  ClearFlagInterlocked(*(_QWORD *)(a2 + 288) + 200LL, 544);
  NtfsUpdateScbFromAttribute(a1, *(_QWORD *)(a2 + 288), v99[0]);
LABEL_175:
  v83 = 0;
  NtfsCleanupAttributeContext(v35, v99);
  memset(v99, 0, 0x58u);
  v38 = NtOfsCreateAttributeEx((_DWORD)a1, v84, (unsigned int)&v95, 128, v24, 1, v36);
  v40 = v38;
  if ( v38 )
  {
    if ( !v82 && v38 == -1073741772 )
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
      NtfsRaiseStatusInternal((_DWORD)a1, -1072103418, 0, v84, 3344249);
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
    NtfsRaiseStatusInternal((_DWORD)a1, v40, 0, v84, 3344254);
  }
  v41 = *(_QWORD *)(a2 + 280);
  if ( (*(_DWORD *)(v41 + 200) & 0x20) == 0 )
    NtfsUpdateScbFromAttribute(a1, *(_QWORD *)(a2 + 280), 0);
  if ( (*(_DWORD *)(v41 + 200) & 8) != 0 )
  {
    v83 = 1;
    LOBYTE(v80) = 0;
    if ( !(unsigned __int8)NtfsLookupInFileRecord(
                             a1,
                             *(_QWORD *)(v41 + 184),
                             *(_QWORD *)(v41 + 184) + 8LL,
                             *(unsigned int *)(v41 + 256),
                             v41 + 264,
                             0,
                             v80,
                             0,
                             0,
                             v99)
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
    NtfsConvertToNonresident((__int64)a1, v84, v99[0], 1u, v99);
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
  v90 = ((*v43 + 4095) / 4096) & 0xFFFFFFF8LL;
  QuadPart = v90 >> 3;
  EndOffset.QuadPart = v90 >> 3;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v90 >> 3, 0x62547854u);
  *(_QWORD *)(a2 + 312) = PoolWithTag;
  memset(PoolWithTag, 0, QuadPart);
  v47 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), QuadPart, 0x62547854u);
  v48 = v47;
  *(_QWORD *)(a2 + 328) = v47;
  v100 = v47;
  v49 = QuadPart >> 2;
  v97 = QuadPart >> 2;
  if ( QuadPart >> 2 )
  {
    if ( ((unsigned __int8)v47 & 4) != 0 )
    {
      *v47 = -1;
      v97 = --v49;
      if ( !v49 )
        goto LABEL_214;
      v48 = v47 + 1;
      v100 = v47 + 1;
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
  v51 = v90;
  v52 = a2 + 280;
  *(_DWORD *)(a2 + 304) = v90;
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
  if ( v82 )
    NtfsSetCcFileSizes(*(_QWORD *)(*(_QWORD *)(v52 + 8) + 280LL), *(_QWORD *)(v52 + 8), *(_QWORD *)(v52 + 8) + 24LL);
  NtfsSetCcFileSizes(*(_QWORD *)(v41 + 280), v41, v41 + 24);
  v63 = *(union _LARGE_INTEGER *)(v41 + 40);
  if ( v63.QuadPart != *(_QWORD *)(v41 + 32) )
  {
    FileOffset = *(union _LARGE_INTEGER *)(v41 + 40);
    v64.QuadPart = *(_QWORD *)(v41 + 32) - 1LL;
    v90 = v64.QuadPart;
    StartOffset = v63;
    while ( v63.QuadPart <= v64.QuadPart )
    {
      EndOffset.QuadPart = v63.QuadPart + 4095;
      if ( v63.QuadPart + 4095 > v64.QuadPart )
        EndOffset = v64;
      CcZeroData(*(PFILE_OBJECT *)(v41 + 280), &StartOffset, &EndOffset, 1u);
      v63.QuadPart = EndOffset.QuadPart + 1;
      StartOffset.QuadPart = EndOffset.QuadPart + 1;
    }
    v65 = v64.QuadPart + 1;
    v90 = v65;
    FsRtlAcquireHeaderMutex(v41 + 120, v41 + 160);
    v66 = *(_DWORD *)(v41 + 200);
    if ( (v66 & 0x20000) == 0 )
      goto LABEL_248;
    v67 = *(_QWORD *)(v41 + 32);
    v68 = *(_QWORD *)(v41 + 464);
    if ( v68 >= v67 )
    {
      if ( *(_QWORD *)(v41 + 40) <= v67 )
        goto LABEL_248;
      if ( *(_QWORD *)(*(_QWORD *)(v41 + 288) + 16LL) && v67 != 0x7FFFFFFFFFFFFFFFLL )
      {
        if ( (__int64)((v67 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v68 )
        {
          v69 = (*(_QWORD *)(v41 + 32) + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
LABEL_247:
          *(_QWORD *)(v41 + 464) = v69;
        }
LABEL_248:
        *(_QWORD *)(v41 + 40) = *(_QWORD *)(v41 + 32);
        FsRtlReleaseHeaderMutex(v41 + 120, v41 + 160);
        CcFlushCache(
          (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v41 + 288) + 16LL),
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
            NtfsStatusTraceAndDebugInternal(a1, (unsigned int)IoStatus.Status, 3344480);
          }
          NtfsRaiseStatusInternal(
            (_DWORD)a1,
            IoStatus.Status,
            *(_QWORD *)(v41 + 184) + 8,
            *(_QWORD *)(v41 + 184),
            3344480);
        }
        LOBYTE(v70) = 1;
        NtfsWriteFileSizes((_DWORD)a1, v41, 0, v70, 1, 1);
        NtfsCheckpointCurrentTransaction(a1);
        goto LABEL_259;
      }
    }
    v69 = *(_QWORD *)(v41 + 32);
    goto LABEL_247;
  }
LABEL_259:
  if ( *(_QWORD *)(v84 + 320) != a2 )
  {
    if ( a2 )
    {
      _InterlockedAdd((volatile signed __int32 *)(a2 + 64), 1u);
      _InterlockedAdd((volatile signed __int32 *)(a2 + 36), 1u);
    }
    v60 = *(_QWORD *)(v84 + 320);
    if ( v60 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v60 + 36));
      v60 = *(_QWORD *)(v84 + 320);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v60 + 64), 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb(*(char **)(v84 + 320));
    }
    *(_QWORD *)(v84 + 320) = a2;
  }
  if ( v85 )
  {
    if ( a1 && a1[7] )
    {
      for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
      {
        v60 = (unsigned int)j;
        v72 = *(_QWORD *)&a1[2 * j + 12];
        if ( !v72 || v72 == v84 )
        {
          *(_QWORD *)&a1[2 * (unsigned int)j + 12] = v84;
          break;
        }
      }
    }
    else
    {
      NtfsReleasePagingResourcePriv(v60, v84, v61, v62);
      if ( a1 )
      {
        v73 = 0;
        v60 = v84;
        do
        {
          if ( *(_QWORD *)&a1[2 * v73 + 12] == v60 )
            *(_QWORD *)&a1[2 * v73 + 12] = 0;
          ++v73;
        }
        while ( v73 != 2 );
      }
    }
  }
  if ( v83 )
    NtfsCleanupAttributeContext(v60, v99);
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
