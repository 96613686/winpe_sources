# NtfsDismountVolume

- ea: `0x14029dd30`
- end: `0x14029ef2c`
- name: `NtfsDismountVolume`
- size: `4604`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x140010be0`
- `0x14001c910`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021e60`
- `0x14003e734`
- `0x14003fe78`
- `0x14004480c`
- `0x1400450dc`
- `0x14004775c`
- `0x1400479cc`
- `0x14004832c`
- `0x14004a178`
- `0x140055024`
- `0x140059234`
- `0x140059250`
- `0x1400b7d0c`
- `0x1400d44bc`
- `0x1400dfe70`
- `0x1400f2460`
- `0x140138c20`
- `0x1401cb2c4`
- `0x1401cec74`
- `0x1401d295c`
- `0x1401d2c34`
- `0x14021e884`
- `0x140230888`
- `0x140299428`
- `0x14029dd30`
- `0x14029f5ac`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14029e7af`
- `ntoskrnl!KeSetEvent` at `0x1402c1611`
- `ntoskrnl!KeSetEvent` at `0x14029e7af`
- `ntoskrnl!KeSetEvent` at `0x1402c1611`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029e2b4`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029ecce`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402c1934`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029e2b4`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029ecce`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402c1934`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029df02`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e298`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e2c0`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029ece4`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029df02`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e298`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e2c0`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029ece4`
- `ntoskrnl!FsRtlDismountComplete` at `0x14029ea85`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402c1660`
- `ntoskrnl!FsRtlDismountComplete` at `0x14029ea85`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402c1660`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029e4c2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029ecb5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c15a6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c191b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029e4c2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029ecb5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c15a6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c191b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14029de51`
- `ntoskrnl!IoGetActivityIdThread` at `0x14029de51`
- `ntoskrnl!KeClearEvent` at `0x14029e73b`
- `ntoskrnl!KeClearEvent` at `0x14029e73b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14029e0d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14029e0d5`

## pseudocode

```c
__int64 __fastcall NtfsDismountVolume(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *ActivityIdThread; // rax
  __int64 v8; // rsi
  int *v9; // r12
  __int64 v10; // rax
  unsigned __int16 v11; // dx
  char v12; // r13
  const WCHAR *v13; // r13
  const WCHAR *v14; // rbx
  int v15; // r10d
  int v16; // r11d
  const WCHAR *v17; // rcx
  const WCHAR *v18; // rcx
  const WCHAR *v19; // rcx
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // edx
  ULONGLONG v25; // rbx
  ULONGLONG v26; // rbx
  __int64 v27; // r9
  const WCHAR *v28; // rcx
  int v29; // r10d
  int v30; // r11d
  const WCHAR *v31; // rcx
  const WCHAR *v32; // rcx
  const WCHAR *v33; // rcx
  const WCHAR *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // edx
  __int64 v38; // r8
  int v39; // eax
  __int64 v40; // r8
  __int64 v41; // rcx
  int v42; // r9d
  int v43; // ecx
  int v44; // eax
  __int64 v45; // rcx
  int v46; // r9d
  __int64 v47; // rdx
  unsigned int v48; // eax
  __int64 v49; // r8
  int v50; // r10d
  int v51; // r11d
  int v52; // ebx
  __int64 v53; // rdx
  unsigned int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // rsi
  __int64 v57; // rcx
  __int64 v58; // r14
  __int64 v59; // r9
  int v60; // r8d
  const WCHAR *v61; // r13
  const WCHAR *v62; // r12
  int v63; // r11d
  int v64; // r15d
  const WCHAR *v65; // rcx
  const WCHAR *v66; // rcx
  const WCHAR *v67; // rcx
  const WCHAR *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // r10
  int v71; // r10d
  ULONGLONG v72; // rsi
  __int16 QuadPart; // r9
  __int64 v75; // rax
  unsigned __int16 v76; // cx
  __int64 v77; // [rsp+B8h] [rbp-238h] BYREF
  __int64 v78; // [rsp+140h] [rbp-1B0h]
  char v79; // [rsp+158h] [rbp-198h] BYREF
  char v80; // [rsp+159h] [rbp-197h]
  char v81; // [rsp+15Ah] [rbp-196h]
  char v82; // [rsp+15Bh] [rbp-195h]
  char v83; // [rsp+15Ch] [rbp-194h]
  int v84; // [rsp+160h] [rbp-190h]
  const WCHAR *v85; // [rsp+168h] [rbp-188h]
  __int64 v86; // [rsp+170h] [rbp-180h]
  __int64 v87; // [rsp+178h] [rbp-178h] BYREF
  const WCHAR *v88; // [rsp+180h] [rbp-170h]
  const WCHAR *v89; // [rsp+188h] [rbp-168h]
  PFILE_OBJECT FileObject; // [rsp+190h] [rbp-160h]
  PFILE_OBJECT v91; // [rsp+198h] [rbp-158h] BYREF
  const WCHAR *v92; // [rsp+1A0h] [rbp-150h]
  ULONGLONG UnbiasedInterruptTime; // [rsp+1A8h] [rbp-148h]
  __int64 v94[2]; // [rsp+1B0h] [rbp-140h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+1C0h] [rbp-130h] BYREF
  int v96; // [rsp+1D0h] [rbp-120h]
  __int64 v97; // [rsp+1D8h] [rbp-118h] BYREF
  struct _UNICODE_STRING v98; // [rsp+1E0h] [rbp-110h] BYREF
  __int64 v99[2]; // [rsp+1F0h] [rbp-100h] BYREF
  __int64 v100; // [rsp+200h] [rbp-F0h]
  __int64 *v101; // [rsp+208h] [rbp-E8h]
  __int128 v102; // [rsp+210h] [rbp-E0h] BYREF
  __int64 v103; // [rsp+220h] [rbp-D0h]
  __int128 v104; // [rsp+228h] [rbp-C8h] BYREF
  __int128 v105; // [rsp+238h] [rbp-B8h] BYREF
  char v106[8]; // [rsp+248h] [rbp-A8h] BYREF

  v101 = &v77;
  v86 = a1;
  v100 = a2;
  v87 = 0;
  v91 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v97 = 0;
  UnbiasedInterruptTime = 0;
  v83 = 0;
  FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(a2 + 184) + 48LL);
  NtfsDecodeFileObject(a1, (_DWORD)FileObject, (unsigned int)&v87, (unsigned int)v94, (__int64)v99, (__int64)&v91, 1);
  if ( a1 && (v4 = *(_QWORD **)(a1 + 120)) != 0 )
  {
    *((_QWORD *)&v102 + 1) = *v4;
    v103 = v4[1];
    *(_QWORD *)&v102 = (char *)&v102 + 8;
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v4);
    if ( ActivityIdThread )
    {
      *((_QWORD *)&v102 + 1) = *ActivityIdThread;
      v103 = ActivityIdThread[1];
      *(_QWORD *)&v102 = (char *)&v102 + 8;
    }
    else
    {
      *(_QWORD *)&v102 = 0;
    }
  }
  v8 = v87;
  v105 = *(_OWORD *)(v87 + 8512);
  v97 = *(_QWORD *)(v87 + 8528);
  LODWORD(v85) = *(_DWORD *)(v87 + 8536);
  v96 = (int)v85;
  if ( (*(_DWORD *)(v87 + 24) & 4) != 0 )
    v104 = *(_OWORD *)(v87 + 7824);
  else
    v104 = 0;
  v9 = (int *)(a1 + 12);
  if ( (*(_DWORD *)(a1 + 12) & 0x40000) == 0 )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    if ( (unsigned __int8)NtfsTelemetryGuard(512) )
      NtfsTelemetryDismountBegin(
        (unsigned int)&v102,
        (unsigned int)&v104,
        (unsigned int)&v105,
        (unsigned int)&v97,
        (_DWORD)v85,
        (*v9 & 1) == 0);
    v83 = 1;
  }
  if ( (*v9 & 0x40000) == 0 )
  {
    if ( dword_140092174
      && (unsigned __int8)(byte_140092178 - 1) > 2u
      && (qword_140092160 & 0x8000000) != 0
      && (qword_140092168 & 0x8000000) == qword_140092168
      && (*(_DWORD *)(a1 + 16) & 0x100000) == 0 )
    {
      v10 = *(_QWORD *)(v8 + 248);
      v11 = *(_WORD *)(v10 + 6);
      if ( v11 > 0x40u || (v11 & 1) != 0 )
        v11 = 0;
      *(_DWORD *)(&UnicodeString.MaximumLength + 1) = 0;
      v5 = 0;
      if ( v11 )
        v5 = v10 + 32;
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000000) != 0 )
        McTemplateU0ppww_EtwWriteTransfer(
          *(unsigned __int16 *)(v8 + 7856) >> 1,
          (unsigned int)fsctrl_c3971,
          a1,
          v8,
          v11 >> 1,
          v5,
          *(_WORD *)(v8 + 7856) >> 1,
          *(_QWORD *)(v8 + 7864));
    }
    NtfsSendBeginDismountEvent(a1, v8, v5, 0);
  }
  if ( !v91 || (v91->CurrentByteOffset.LowPart & 0x200) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      if ( v91 )
        QuadPart = v91->CurrentByteOffset.QuadPart;
      else
        LOBYTE(QuadPart) = 0;
      v75 = *(_QWORD *)(v8 + 248);
      v76 = *(_WORD *)(v75 + 6);
      if ( v76 > 0x40u || (v76 & 1) != 0 )
        v76 = 0;
      McTemplateU0ppwwd_EtwWriteTransfer(
        v76 >> 1,
        (unsigned int)fsctrl_c3986,
        (unsigned int)KeGetCurrentThread(),
        v8,
        *(_WORD *)(v8 + 7872) >> 1,
        *(_QWORD *)(v8 + 7880),
        v76 >> 1,
        v75 + 32,
        QuadPart);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225506LL, 1183645);
    LOBYTE(v6) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225506LL, v6, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225506LL, 1183646);
    return 3221225506LL;
  }
  v91 = FileObject;
  v99[0] = a1 + 12;
  v84 = -1073741823;
  v80 = 0;
  v82 = 0;
  v81 = 0;
  v12 = 1;
  if ( (*v9 & 0x40000) == 0 )
  {
    UnicodeString = 0;
    v79 = 0;
    KeWaitForSingleObject((PVOID)(v8 + 6632), Executive, 0, 0, 0);
    NtfsFillVcbVolumeGuid(a1);
    NtfsRepairGetVolumeId(a1, v8, 0, (unsigned int)&UnicodeString, (__int64)&v79);
    v13 = &word_140064400;
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v14 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6736) )
        v14 = *(const WCHAR **)(v8 + 6736);
      v15 = (*(_DWORD *)(v8 + 28) >> 2) & 1;
      v16 = *(_DWORD *)(v8 + 6660);
      if ( (unsigned int)(v16 - 1) > 0x13 )
        LOBYTE(v16) = 0;
      v17 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6720) )
        v17 = *(const WCHAR **)(v8 + 6720);
      v92 = v17;
      v18 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6704) )
        v18 = *(const WCHAR **)(v8 + 6704);
      v85 = v18;
      v19 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6688) )
        v19 = *(const WCHAR **)(v8 + 6688);
      v88 = v19;
      v20 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6672) )
        v20 = *(const WCHAR **)(v8 + 6672);
      v89 = v20;
      v21 = &word_140064400;
      if ( *(_QWORD *)(v8 + 7864) )
        v21 = *(const WCHAR **)(v8 + 7864);
      v94[0] = (__int64)v21;
      if ( (*(_DWORD *)(v8 + 4) & 0xC00) != 0x800
        && (v22 = *(_QWORD *)(v8 + 248)) != 0
        && (v23 = *(_QWORD *)(v22 + 16)) != 0 )
      {
        v24 = (*(_DWORD *)(v23 + 48) >> 8) & 1;
      }
      else
      {
        v24 = 0;
      }
      McTemplateK0jmztzzzzzqjqtz_EtwWriteTransfer(
        v8 + 7808,
        v24,
        v102,
        v8 + 7824,
        v8 + 8528,
        (__int64)UnicodeString.Buffer,
        v24,
        v94[0],
        (__int64)v89,
        (__int64)v88,
        (__int64)v85,
        (__int64)v92,
        v16,
        v8 + 7808,
        *(_DWORD *)(v8 + 6792),
        v15,
        (__int64)v14);
    }
    v25 = KeQueryUnbiasedInterruptTime();
    FsRtlNotifyVolumeEvent(FileObject, 1u);
    v26 = (KeQueryUnbiasedInterruptTime() - v25) / 0xA / 0x3E8;
    IoPerfPrintTimeInterval(v26, 2, v106, v27);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v28 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6736) )
        v28 = *(const WCHAR **)(v8 + 6736);
      v94[0] = (__int64)v28;
      v29 = (*(_DWORD *)(v8 + 28) >> 2) & 1;
      v30 = *(_DWORD *)(v8 + 6660);
      if ( (unsigned int)(v30 - 1) > 0x13 )
        LOBYTE(v30) = 0;
      v31 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6720) )
        v31 = *(const WCHAR **)(v8 + 6720);
      v89 = v31;
      v32 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6704) )
        v32 = *(const WCHAR **)(v8 + 6704);
      v88 = v32;
      v33 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6688) )
        v33 = *(const WCHAR **)(v8 + 6688);
      v92 = v33;
      v34 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6672) )
        v34 = *(const WCHAR **)(v8 + 6672);
      v85 = v34;
      if ( *(_QWORD *)(v8 + 7864) )
        v13 = *(const WCHAR **)(v8 + 7864);
      if ( (*(_DWORD *)(v8 + 4) & 0xC00) != 0x800
        && (v35 = *(_QWORD *)(v8 + 248)) != 0
        && (v36 = *(_QWORD *)(v35 + 16)) != 0 )
      {
        v37 = (*(_DWORD *)(v36 + 48) >> 8) & 1;
      }
      else
      {
        v37 = 0;
      }
      McTemplateK0jmztzzzzzqjqtzzx_EtwWriteTransfer(
        v8 + 7808,
        v37,
        v102,
        v8 + 7824,
        v8 + 8528,
        (__int64)UnicodeString.Buffer,
        v37,
        (__int64)v13,
        (__int64)v85,
        (__int64)v92,
        (__int64)v88,
        (__int64)v89,
        v30,
        v8 + 7808,
        *(_DWORD *)(v8 + 6792),
        v29,
        v94[0],
        (__int64)v106,
        v26);
    }
    if ( v79 )
      RtlFreeUnicodeString(&UnicodeString);
    v12 = 1;
  }
  while ( 1 )
  {
    NtfsPurgeFileRecordCache(a1);
    NtfsAcquireCheckpointSynchronization(a1, v8, 80);
    v81 = 1;
    LOBYTE(v38) = 1;
    NtfsAcquireExclusiveVcb(a1, v8, v38);
    v80 = 1;
    if ( *(_DWORD *)(v8 + 280) )
    {
      v46 = *(_DWORD *)(v8 + 4);
      if ( (v46 & 2) != 0 )
      {
        v50 = *(_DWORD *)(v8 + 260);
        v51 = *(_DWORD *)(v8 + 268);
        v52 = *(_DWORD *)(v8 + 264);
        if ( v52 == v50 + ~v51 )
        {
          if ( NtfsStatusDebugFlags )
          {
            v40 = 1183785;
LABEL_118:
            NtfsStatusTraceAndDebugInternal(0, 3221226685LL, v40);
          }
LABEL_119:
          v84 = -1073740611;
          goto LABEL_131;
        }
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v53 = *(_QWORD *)(v8 + 248);
          v54 = *(unsigned __int16 *)(v53 + 6);
          if ( v54 > 0x40 || (v54 & 1) != 0 )
            v54 = 0;
          LODWORD(FileObject) = v54;
          LOWORD(v94[0]) = v54;
          v94[1] = v53 + 32;
          McTemplateU0ppwwdddd_EtwWriteTransfer(
            *(unsigned __int16 *)(v8 + 7872) >> 1,
            (unsigned int)fsctrl_c4145,
            (unsigned int)KeGetCurrentThread(),
            v8,
            *(_WORD *)(v8 + 7872) >> 1,
            *(_QWORD *)(v8 + 7880),
            (unsigned __int16)v54 >> 1,
            v53 + 32,
            v46,
            v52,
            v50,
            v51);
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_130;
        v49 = 1183807;
      }
      else
      {
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v47 = *(_QWORD *)(v8 + 248);
          v48 = *(unsigned __int16 *)(v47 + 6);
          if ( v48 > 0x40 || (v48 & 1) != 0 )
            v48 = 0;
          LODWORD(v92) = v48;
          LOWORD(v99[0]) = v48;
          v99[1] = v47 + 32;
          McTemplateU0ppwwd_EtwWriteTransfer(
            *(unsigned __int16 *)(v8 + 7872) >> 1,
            (unsigned int)fsctrl_c4117,
            (unsigned int)KeGetCurrentThread(),
            v8,
            *(_WORD *)(v8 + 7872) >> 1,
            *(_QWORD *)(v8 + 7880),
            (unsigned __int16)v48 >> 1,
            v47 + 32,
            v46);
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_130;
        v49 = 1183776;
      }
      NtfsStatusTraceAndDebugInternal(0, 3221225506LL, v49);
LABEL_130:
      v84 = -1073741790;
      goto LABEL_131;
    }
    v82 = 1;
    v39 = *(_DWORD *)(v8 + 4);
    if ( (v39 & 1) == 0 )
      break;
    if ( (unsigned __int8)NtfsIsDismountProtectedStateSepVolume(a1, *(_QWORD *)(v8 + 224)) )
    {
      if ( NtfsStatusDebugFlags )
      {
        v40 = 1183847;
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    v94[0] = v8 + 4;
    v88 = (const WCHAR *)(v8 + 4);
    if ( !v12 )
    {
      v89 = (const WCHAR *)(v8 + 5521);
      if ( !*(_BYTE *)(v8 + 5521) && NtfsFlushTrimRequestsOnDismount )
        NtfsFlushAllTrimHintsSynchronous(a1, v8);
      *(_BYTE *)(v8 + 5521) = 1;
      v43 = *v9;
      if ( (*v9 & 0x40000) == 0 && (*(_DWORD *)(v8 + 4) & 0x2000000) == 0 )
      {
        *(_DWORD *)(a1 + 392) = 8;
        *v9 = v43 | 0x40000;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225864LL, 1183951);
        NtfsRaiseStatusInternal(a1, -1073741432, 0, 0, 1183951);
        __debugbreak();
        JUMPOUT(0x14029EF2CLL);
      }
      if ( (*(_DWORD *)(v8 + 24) & 0x40000) != 0 )
      {
        KeClearEvent(*(PRKEVENT *)(v8 + 1432));
        v44 = NtfsFlushVolume(a1);
        v84 = v44;
        if ( (*(_DWORD *)(v8 + 24) & 0x40000) != 0
          && ((v45 = *(_QWORD *)(v8 + 64)) == 0 || (*(_DWORD *)(v45 + 200) & 0x20000) != 0)
          || v44 != -1073741797 && !(unsigned __int8)NtfsAreClustersDangling(a1, v8) )
        {
          NtfsFlushVolume(a1);
          KeSetEvent(*(PRKEVENT *)(v8 + 1432), 0, 0);
          goto LABEL_103;
        }
        NtfsFlushVolume(a1);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221226652LL, 1184020);
        v84 = -1073740644;
        local_unwind_0(v101, &loc_14029EA45);
      }
      NtfsFlushVolume(a1);
LABEL_103:
      NtfsPerformDismountOnVcb((_DWORD *)a1, v8, 0, 0, 0, 0);
      SetFlagInterlocked(v88, 2);
      *(_QWORD *)(v8 + 1472) = (char *)&FileObject->Type + 1;
      NtfsSetDirectWritesAllowed(*(_QWORD *)(v8 + 248));
LABEL_104:
      v84 = 0;
      goto LABEL_131;
    }
    NtfsReleaseVcb(a1, v8);
    v80 = 0;
    NtfsReleaseCheckpointSynchronization(v41, v8, 16);
    v81 = 0;
    TxfShutdownVolume(a1, v8, 0, v42, 0);
    v12 = 0;
  }
  if ( (v39 & 0x800000) == 0 )
    goto LABEL_104;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 1183833);
  v84 = -1073741202;
LABEL_131:
  v55 = v84;
  if ( v84 || !v82 )
  {
    v56 = v87;
  }
  else
  {
    v56 = v87;
    SetFlagInterlocked(v87 + 4, 0x800000);
  }
  FsRtlDismountComplete(*(_QWORD *)(v56 + 224), v55);
  NtfsReleaseCheckpointSynchronization(v57, v56, 16);
  v58 = v86;
  if ( (v55 & 0x80000000) != 0 )
    NtfsUpdateDeleteNotificationVolumeSetting(v86, v56, 0);
  NtfsReleaseVcb(v58, v56);
  if ( (int)(v55 + 0x80000000) >= 0 && v55 != -1073741202 )
  {
    v98 = 0;
    v79 = 0;
    NtfsFillVcbVolumeGuid(v58);
    LOBYTE(v60) = 1;
    NtfsRepairGetVolumeId(v58, *(_QWORD *)(v58 + 104), v60, (unsigned int)&v98, (__int64)&v79);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x80000) != 0 )
    {
      v61 = &word_140064400;
      v62 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6736) )
        v62 = *(const WCHAR **)(v56 + 6736);
      v63 = (*(_DWORD *)(v56 + 28) >> 2) & 1;
      v64 = *(_DWORD *)(v56 + 6660);
      if ( (unsigned int)(v64 - 1) > 0x13 )
        LOBYTE(v64) = 0;
      v65 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6720) )
        v65 = *(const WCHAR **)(v56 + 6720);
      v99[0] = (__int64)v65;
      v66 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6704) )
        v66 = *(const WCHAR **)(v56 + 6704);
      v94[0] = (__int64)v66;
      v67 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6688) )
        v67 = *(const WCHAR **)(v56 + 6688);
      v89 = v67;
      v68 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6672) )
        v68 = *(const WCHAR **)(v56 + 6672);
      v88 = v68;
      if ( *(_QWORD *)(v56 + 7864) )
        v61 = *(const WCHAR **)(v56 + 7864);
      if ( (*(_DWORD *)(v56 + 4) & 0xC00) != 0x800
        && (v69 = *(_QWORD *)(v56 + 248)) != 0
        && (v70 = *(_QWORD *)(v69 + 16)) != 0 )
      {
        v71 = (*(_DWORD *)(v70 + 48) >> 8) & 1;
      }
      else
      {
        LOBYTE(v71) = 0;
      }
      McTemplateK0jmztzzzzzqjqtzpd_EtwWriteTransfer(
        v56 + 7808,
        v56 + 8528,
        v102,
        v56 + 7824,
        v56 + 8528,
        (__int64)v98.Buffer,
        v71,
        (__int64)v61,
        (__int64)v88,
        (__int64)v89,
        v94[0],
        v99[0],
        v64,
        v56 + 7808,
        *(_DWORD *)(v56 + 6792),
        v63,
        (__int64)v62,
        v78,
        v55);
    }
    if ( v79 )
      RtlFreeUnicodeString(&v98);
    FsRtlNotifyVolumeEvent(v91, 2u);
  }
  if ( v83 )
  {
    v72 = KeQueryUnbiasedInterruptTime();
    if ( (unsigned __int8)NtfsTelemetryGuard(512) )
      NtfsTelemetryDismountEnd(
        (unsigned int)&v102,
        (unsigned int)&v104,
        (unsigned int)&v105,
        (unsigned int)&v97,
        v96,
        v55,
        v72 - UnbiasedInterruptTime);
  }
  if ( NtfsStatusDebugFlags && v55 && v55 - 298 > 1 && v55 + 2147483643 > 1 )
    NtfsStatusTraceAndDebugInternal(v58, v55, 1184192);
  LOBYTE(v59) = v100 != 0;
  NtfsExtendedCompleteRequestInternal(v58, v100, v55, v59, (v55 & 0x80000000) == 0);
  return v55;
}

```

## disassembly

```asm
0x14029dd30  mov     r11, rsp
0x14029dd33  mov     [r11+18h], rbx
0x14029dd37  mov     [r11+20h], rsi
0x14029dd3b  push    rdi
0x14029dd3c  push    r12
0x14029dd3e  push    r13
0x14029dd40  push    r14
0x14029dd42  push    r15
0x14029dd44  sub     rsp, 210h
0x14029dd4b  mov     rax, cs:__security_cookie
0x14029dd52  xor     rax, rsp
0x14029dd55  mov     [rsp+238h+var_38], rax
0x14029dd5d  mov     [rsp+238h+var_E8], rsp
0x14029dd65  mov     rbx, rdx
0x14029dd68  mov     r14, rcx
0x14029dd6b  mov     [rsp+238h+var_180], rcx
0x14029dd73  mov     [rsp+238h+var_F0], rdx
0x14029dd7b  xor     edi, edi
0x14029dd7d  mov     [r11-178h], rdi
0x14029dd84  mov     [r11-158h], rdi
0x14029dd8b  xorps   xmm0, xmm0
0x14029dd8e  xor     eax, eax
0x14029dd90  movups  [rsp+238h+var_E0], xmm0
0x14029dd98  mov     [r11-0D0h], rax
0x14029dd9f  movups  [rsp+238h+var_C8], xmm0
0x14029dda7  xorps   xmm1, xmm1
0x14029ddaa  movups  [rsp+238h+var_B8], xmm1
0x14029ddb2  mov     [r11-118h], rdi
0x14029ddb9  mov     [rsp+238h+var_148], rdi
0x14029ddc1  mov     [rsp+238h+var_194], dil
0x14029ddc9  mov     rax, [rdx+0B8h]
0x14029ddd0  mov     rax, [rax+30h]
0x14029ddd4  mov     [rsp+238h+FileObject], rax
0x14029dddc  mov     byte ptr [rsp+238h+var_208], 1
0x14029dde1  lea     rcx, [r11-158h]
0x14029dde8  mov     [rsp+238h+var_210], rcx
0x14029dded  lea     rcx, [r11-100h]
0x14029ddf4  mov     [rsp+238h+Timeout], rcx
0x14029ddf9  lea     r9, [r11-140h]
0x14029de00  lea     r8, [r11-178h]
0x14029de07  mov     rdx, rax
0x14029de0a  mov     rcx, r14
0x14029de0d  call    NtfsDecodeFileObject
0x14029de12  test    r14, r14
0x14029de15  jz      short loc_14029DE51
0x14029de17  mov     rcx, [r14+78h]
0x14029de1b  test    rcx, rcx
0x14029de1e  jz      short loc_14029DE51
0x14029de20  mov     rax, [rcx]
0x14029de23  mov     qword ptr [rsp+238h+var_E0+8], rax
0x14029de2b  mov     rax, [rcx+8]
0x14029de2f  mov     [rsp+238h+var_D0], rax
0x14029de37  lea     rax, [rsp+238h+var_E0+8]
0x14029de3f  mov     qword ptr [rsp+238h+var_E0], rax
0x14029de47  mov     rax, qword ptr [rsp+238h+var_E0]
0x14029de4f  jmp     short loc_14029DE93
0x14029de51  call    cs:__imp_IoGetActivityIdThread
0x14029de58  nop     dword ptr [rax+rax+00h]
0x14029de5d  test    rax, rax
0x14029de60  jz      short loc_14029DE8B
0x14029de62  mov     rcx, [rax]
0x14029de65  mov     qword ptr [rsp+238h+var_E0+8], rcx
0x14029de6d  mov     rax, [rax+8]
0x14029de71  mov     [rsp+238h+var_D0], rax
0x14029de79  lea     rax, [rsp+238h+var_E0+8]
0x14029de81  mov     qword ptr [rsp+238h+var_E0], rax
0x14029de89  jmp     short loc_14029DE93
0x14029de8b  mov     qword ptr [rsp+238h+var_E0], rdi
0x14029de93  mov     rsi, [rsp+238h+var_178]
0x14029de9b  movups  xmm0, xmmword ptr [rsi+2140h]
0x14029dea2  movdqu  [rsp+238h+var_B8], xmm0
0x14029deab  mov     rax, [rsi+2150h]
0x14029deb2  mov     [rsp+238h+var_118], rax
0x14029deba  mov     eax, [rsi+2158h]
0x14029dec0  mov     dword ptr [rsp+238h+var_188], eax
0x14029dec7  mov     [rsp+238h+var_120], eax
0x14029dece  mov     eax, [rsi+18h]
0x14029ded1  test    al, 4
0x14029ded3  jz      short loc_14029DEE7
0x14029ded5  movups  xmm0, xmmword ptr [rsi+1E90h]
0x14029dedc  movdqu  [rsp+238h+var_C8], xmm0
0x14029dee5  jmp     short loc_14029DEF2
0x14029dee7  xorps   xmm0, xmm0
0x14029deea  movups  [rsp+238h+var_C8], xmm0
0x14029def2  lea     r12, [r14+0Ch]
0x14029def6  mov     r15d, 40000h
0x14029defc  test    [r12], r15d
0x14029df00  jnz     short loc_14029DF6E
0x14029df02  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14029df09  nop     dword ptr [rax+rax+00h]
0x14029df0e  mov     [rsp+238h+var_148], rax
0x14029df16  mov     r13d, 200h
0x14029df1c  mov     ecx, r13d
0x14029df1f  call    NtfsTelemetryGuard
0x14029df24  test    al, al
0x14029df26  jz      short loc_14029DF64
0x14029df28  mov     eax, [r12]
0x14029df2c  not     al
0x14029df2e  and     al, 1
0x14029df30  mov     byte ptr [rsp+238h+var_210], al
0x14029df34  mov     eax, dword ptr [rsp+238h+var_188]
0x14029df3b  mov     dword ptr [rsp+238h+Timeout], eax
0x14029df3f  lea     r9, [rsp+238h+var_118]
0x14029df47  lea     r8, [rsp+238h+var_B8]
0x14029df4f  lea     rdx, [rsp+238h+var_C8]
0x14029df57  lea     rcx, [rsp+238h+var_E0]
0x14029df5f  call    NtfsTelemetryDismountBegin
0x14029df64  mov     [rsp+238h+var_194], 1
0x14029df6c  jmp     short loc_14029DF74
0x14029df6e  mov     r13d, 200h
0x14029df74  test    [r12], r15d
0x14029df78  jnz     loc_14029E047
0x14029df7e  cmp     cs:dword_140092174, edi
0x14029df84  jz      loc_14029E039
0x14029df8a  mov     al, cs:byte_140092178
0x14029df90  dec     al
0x14029df92  cmp     al, 2
0x14029df94  jbe     loc_14029E039
0x14029df9a  mov     edx, 8000000h
0x14029df9f  test    cs:qword_140092160, rdx
0x14029dfa6  jz      loc_14029E039
0x14029dfac  mov     rax, cs:qword_140092168
0x14029dfb3  and     rax, rdx
0x14029dfb6  cmp     rax, cs:qword_140092168
0x14029dfbd  jnz     short loc_14029E039
0x14029dfbf  mov     eax, [r14+10h]
0x14029dfc3  bt      rax, 14h
0x14029dfc8  jb      short loc_14029E039
0x14029dfca  mov     rax, [rsi+0F8h]
0x14029dfd1  movzx   edx, word ptr [rax+6]
0x14029dfd5  cmp     dx, 40h ; '@'
0x14029dfd9  ja      short loc_14029DFE0
0x14029dfdb  test    dl, 1
0x14029dfde  jz      short loc_14029DFE2
0x14029dfe0  mov     edx, edi
0x14029dfe2  xor     ecx, ecx
0x14029dfe4  mov     dword ptr [rsp+238h+UnicodeString+4], ecx
0x14029dfeb  mov     r8, rdi
0x14029dfee  test    dx, dx
0x14029dff1  jz      short loc_14029DFF7
0x14029dff3  lea     r8, [rax+20h]
0x14029dff7  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 4
0x14029dffe  jz      short loc_14029E039
0x14029e000  movzx   ecx, word ptr [rsi+1EB0h]
0x14029e007  shr     ecx, 1
0x14029e009  movzx   edx, dx
0x14029e00c  shr     edx, 1
0x14029e00e  mov     rax, [rsi+1EB8h]
0x14029e015  mov     [rsp+238h+var_200], rax
0x14029e01a  mov     dword ptr [rsp+238h+var_208], ecx
0x14029e01e  mov     [rsp+238h+var_210], r8
0x14029e023  mov     dword ptr [rsp+238h+Timeout], edx
0x14029e027  mov     r9, rsi
0x14029e02a  mov     r8, r14
0x14029e02d  lea     rdx, fsctrl_c3971
0x14029e034  call    McTemplateU0ppww_EtwWriteTransfer
0x14029e039  xor     r9d, r9d
0x14029e03c  mov     rdx, rsi
0x14029e03f  mov     rcx, r14
0x14029e042  call    NtfsSendBeginDismountEvent
0x14029e047  mov     rcx, [rsp+238h+var_158]
0x14029e04f  test    rcx, rcx
0x14029e052  jz      loc_14029EDD2
0x14029e058  test    [rcx+68h], r13w
0x14029e05d  jz      loc_14029EDD2
0x14029e063  mov     rax, [rsp+238h+FileObject]
0x14029e06b  mov     [rsp+238h+var_158], rax
0x14029e073  mov     [rsp+238h+var_100], r12
0x14029e07b  mov     [rsp+238h+var_190], 0C0000001h
0x14029e086  mov     [rsp+238h+var_197], dil
0x14029e08e  mov     [rsp+238h+var_195], dil
0x14029e096  mov     [rsp+238h+var_196], dil
0x14029e09e  mov     r13b, 1
0x14029e0a1  mov     eax, [r12]
0x14029e0a5  test    r15d, eax
0x14029e0a8  jnz     loc_14029E4D1
0x14029e0ae  xorps   xmm0, xmm0
0x14029e0b1  movups  xmmword ptr [rsp+238h+UnicodeString.Length], xmm0
0x14029e0b9  mov     [rsp+238h+var_198], dil
0x14029e0c1  lea     rcx, [rsi+19E8h]; Object
0x14029e0c8  mov     [rsp+238h+Timeout], rdi; Timeout
0x14029e0cd  xor     r9d, r9d; Alertable
0x14029e0d0  xor     r8d, r8d; WaitMode
0x14029e0d3  xor     edx, edx; WaitReason
0x14029e0d5  call    cs:__imp_KeWaitForSingleObject
0x14029e0dc  nop     dword ptr [rax+rax+00h]
0x14029e0e1  nop
0x14029e0e2  mov     rcx, r14
0x14029e0e5  call    NtfsFillVcbVolumeGuid
0x14029e0ea  lea     rax, [rsp+238h+var_198]
0x14029e0f2  mov     [rsp+238h+Timeout], rax
0x14029e0f7  lea     r9, [rsp+238h+UnicodeString]
0x14029e0ff  xor     r8d, r8d
0x14029e102  mov     rdx, rsi
0x14029e105  mov     rcx, r14
0x14029e108  call    NtfsRepairGetVolumeId
0x14029e10d  lea     r13, word_140064400
0x14029e114  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+2, 4
0x14029e11b  jz      loc_14029E298
0x14029e121  mov     rax, [rsi+1A50h]
0x14029e128  mov     rbx, r13
0x14029e12b  test    rax, rax
0x14029e12e  cmovnz  rbx, rax
0x14029e132  mov     r10d, [rsi+1Ch]
0x14029e136  shr     r10d, 2
0x14029e13a  and     r10d, 1
0x14029e13e  mov     r11d, [rsi+1A04h]
0x14029e145  lea     eax, [r11-1]
0x14029e149  cmp     eax, 13h
0x14029e14c  cmova   r11d, edi
0x14029e150  mov     rax, [rsi+1A40h]
0x14029e157  mov     rcx, r13
0x14029e15a  test    rax, rax
0x14029e15d  cmovnz  rcx, rax
0x14029e161  mov     [rsp+238h+var_150], rcx
0x14029e169  mov     rax, [rsi+1A30h]
0x14029e170  mov     rcx, r13
0x14029e173  test    rax, rax
0x14029e176  cmovnz  rcx, rax
0x14029e17a  mov     [rsp+238h+var_188], rcx
0x14029e182  mov     rax, [rsi+1A20h]
0x14029e189  mov     rcx, r13
0x14029e18c  test    rax, rax
0x14029e18f  cmovnz  rcx, rax
0x14029e193  mov     [rsp+238h+var_170], rcx
0x14029e19b  mov     rax, [rsi+1A10h]
0x14029e1a2  mov     rcx, r13
0x14029e1a5  test    rax, rax
0x14029e1a8  cmovnz  rcx, rax
0x14029e1ac  mov     [rsp+238h+var_168], rcx
0x14029e1b4  mov     rax, [rsi+1EB8h]
0x14029e1bb  mov     rcx, r13
0x14029e1be  test    rax, rax
0x14029e1c1  cmovnz  rcx, rax
0x14029e1c5  mov     [rsp+238h+var_140], rcx
0x14029e1cd  mov     eax, [rsi+4]
0x14029e1d0  and     eax, 0C00h
0x14029e1d5  cmp     eax, 800h
0x14029e1da  jz      short loc_14029E1FC
0x14029e1dc  mov     rax, [rsi+0F8h]
0x14029e1e3  test    rax, rax
0x14029e1e6  jz      short loc_14029E1FC
0x14029e1e8  mov     rdx, [rax+10h]
0x14029e1ec  test    rdx, rdx
0x14029e1ef  jz      short loc_14029E1FC
0x14029e1f1  mov     edx, [rdx+30h]
0x14029e1f4  shr     edx, 8
0x14029e1f7  and     edx, 1
0x14029e1fa  jmp     short loc_14029E1FE
0x14029e1fc  mov     edx, edi
0x14029e1fe  mov     r8, qword ptr [rsp+238h+var_E0]
0x14029e206  lea     rcx, [rsi+1E80h]
0x14029e20d  lea     r9, [rsi+1E90h]
0x14029e214  mov     [rsp+238h+var_1B8], rbx
0x14029e21c  mov     [rsp+238h+var_1C0], r10d
0x14029e221  mov     eax, [rsi+1A88h]
0x14029e227  mov     [rsp+238h+var_1C8], eax
0x14029e22b  mov     [rsp+238h+var_1D0], rcx
0x14029e230  mov     [rsp+238h+var_1D8], r11d
0x14029e235  mov     rax, [rsp+238h+var_150]
0x14029e23d  mov     [rsp+238h+var_1E0], rax
0x14029e242  mov     rax, [rsp+238h+var_188]
0x14029e24a  mov     [rsp+238h+var_1E8], rax
0x14029e24f  mov     rax, [rsp+238h+var_170]
0x14029e257  mov     [rsp+238h+var_1F0], rax
0x14029e25c  mov     rax, [rsp+238h+var_168]
0x14029e264  mov     [rsp+238h+var_1F8], rax
0x14029e269  mov     rax, [rsp+238h+var_140]
0x14029e271  mov     [rsp+238h+var_200], rax
0x14029e276  mov     dword ptr [rsp+238h+var_208], edx
0x14029e27a  mov     rax, [rsp+238h+UnicodeString.Buffer]
0x14029e282  mov     [rsp+238h+var_210], rax
0x14029e287  lea     rax, [rsi+2150h]
0x14029e28e  mov     [rsp+238h+Timeout], rax
0x14029e293  call    McTemplateK0jmztzzzzzqjqtz_EtwWriteTransfer
0x14029e298  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14029e29f  nop     dword ptr [rax+rax+00h]
0x14029e2a4  mov     rbx, rax
0x14029e2a7  mov     edx, 1; EventCode
0x14029e2ac  mov     rcx, [rsp+238h+FileObject]; FileObject
0x14029e2b4  call    cs:__imp_FsRtlNotifyVolumeEvent
0x14029e2bb  nop     dword ptr [rax+rax+00h]
0x14029e2c0  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14029e2c7  nop     dword ptr [rax+rax+00h]
0x14029e2cc  mov     rcx, rax
0x14029e2cf  sub     rcx, rbx
0x14029e2d2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14029e2dc  mul     rcx
0x14029e2df  mov     rbx, rdx
0x14029e2e2  shr     rbx, 3
0x14029e2e6  mov     rax, 624DD2F1A9FBE77h
0x14029e2f0  mul     rbx
0x14029e2f3  sub     rbx, rdx
0x14029e2f6  shr     rbx, 1
0x14029e2f9  add     rbx, rdx
0x14029e2fc  shr     rbx, 9
0x14029e300  lea     r8, [rsp+238h+var_A8]
0x14029e308  mov     edx, 2
0x14029e30d  mov     rcx, rbx
0x14029e310  call    IoPerfPrintTimeInterval
  ... truncated ...
```
