# NtfsDismountVolume

- ea: `0x14029dd30`
- end: `0x14029ef2c`
- name: `NtfsDismountVolume`
- size: `4604`
- prototype: `__int64 __fastcall(__int64, IRP *)`
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
__int64 __fastcall NtfsDismountVolume(__int64 a1, IRP *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // r8
  _QWORD *ActivityIdThread; // rax
  __int64 v7; // rsi
  int *v8; // r12
  __int64 v9; // rax
  unsigned __int16 v10; // dx
  __int64 v11; // rcx
  char v12; // r13
  const wchar_t *v13; // r13
  const wchar_t *v14; // rbx
  int v15; // r10d
  int v16; // r11d
  const wchar_t *v17; // rcx
  const wchar_t *v18; // rcx
  unsigned int *v19; // rcx
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  ULONGLONG v25; // rbx
  ULONGLONG v26; // rbx
  const wchar_t *v27; // rcx
  int v28; // r10d
  int v29; // r11d
  const wchar_t *v30; // rcx
  unsigned int *v31; // rcx
  const wchar_t *v32; // rcx
  const wchar_t *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // r8
  unsigned int v39; // r8d
  __int64 v40; // rcx
  __int64 v41; // r9
  int v42; // ecx
  int v43; // eax
  char v44; // r8
  __int64 v45; // rcx
  int v46; // r9d
  __int64 v47; // rdx
  unsigned int v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // r8d
  int v51; // r10d
  int v52; // r11d
  int v53; // ebx
  __int64 v54; // rdx
  unsigned int v55; // eax
  __int64 v56; // rcx
  int v57; // ebx
  __int64 v58; // rsi
  __int64 v59; // rcx
  __int64 v60; // r14
  const wchar_t *v61; // r13
  const wchar_t *v62; // r12
  int v63; // r11d
  int v64; // r15d
  const wchar_t *v65; // rcx
  const wchar_t *v66; // rcx
  const wchar_t *v67; // rcx
  unsigned int *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // r10
  int v71; // r10d
  ULONGLONG v72; // rsi
  int LowPart_low; // r9d
  __int64 v75; // rax
  unsigned __int16 v76; // cx
  __int64 v77; // rcx
  int v78; // edx
  __int64 v79; // [rsp+B8h] [rbp-238h] BYREF
  PLARGE_INTEGER Timeout; // [rsp+D8h] [rbp-218h]
  __int64 v81; // [rsp+E0h] [rbp-210h]
  __int64 v82; // [rsp+E8h] [rbp-208h]
  __int64 v83; // [rsp+F0h] [rbp-200h]
  __int64 v84; // [rsp+F8h] [rbp-1F8h]
  __int64 v85; // [rsp+100h] [rbp-1F0h]
  __int64 v86; // [rsp+108h] [rbp-1E8h]
  __int64 v87; // [rsp+110h] [rbp-1E0h]
  __int64 v88; // [rsp+140h] [rbp-1B0h]
  char v89; // [rsp+158h] [rbp-198h] BYREF
  char v90; // [rsp+159h] [rbp-197h]
  char v91; // [rsp+15Ah] [rbp-196h]
  char v92; // [rsp+15Bh] [rbp-195h]
  char v93; // [rsp+15Ch] [rbp-194h]
  int v94; // [rsp+160h] [rbp-190h]
  const wchar_t *v95; // [rsp+168h] [rbp-188h]
  __int64 v96; // [rsp+170h] [rbp-180h]
  __int64 v97; // [rsp+178h] [rbp-178h] BYREF
  wchar_t *v98; // [rsp+180h] [rbp-170h]
  const wchar_t *v99; // [rsp+188h] [rbp-168h]
  PFILE_OBJECT FileObject; // [rsp+190h] [rbp-160h]
  PFILE_OBJECT v101; // [rsp+198h] [rbp-158h] BYREF
  const wchar_t *v102; // [rsp+1A0h] [rbp-150h]
  ULONGLONG UnbiasedInterruptTime; // [rsp+1A8h] [rbp-148h]
  const wchar_t *v104[2]; // [rsp+1B0h] [rbp-140h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+1C0h] [rbp-130h] BYREF
  int v106; // [rsp+1D0h] [rbp-120h]
  __int64 v107; // [rsp+1D8h] [rbp-118h] BYREF
  struct _UNICODE_STRING v108; // [rsp+1E0h] [rbp-110h] BYREF
  const wchar_t *v109[2]; // [rsp+1F0h] [rbp-100h] BYREF
  IRP *v110; // [rsp+200h] [rbp-F0h]
  __int64 *v111; // [rsp+208h] [rbp-E8h]
  __int128 v112; // [rsp+210h] [rbp-E0h] BYREF
  __int64 v113; // [rsp+220h] [rbp-D0h]
  __int128 v114; // [rsp+228h] [rbp-C8h] BYREF
  __int128 v115; // [rsp+238h] [rbp-B8h] BYREF
  unsigned __int16 v116; // [rsp+248h] [rbp-A8h] BYREF

  v111 = &v79;
  v96 = a1;
  v110 = a2;
  v97 = 0;
  v101 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v107 = 0;
  UnbiasedInterruptTime = 0;
  v93 = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  NtfsDecodeFileObject(a1, (__int64)FileObject, &v97, v104, v109, &v101, 1);
  if ( a1 && (v4 = *(_QWORD **)(a1 + 120)) != 0 )
  {
    *((_QWORD *)&v112 + 1) = *v4;
    v113 = v4[1];
    *(_QWORD *)&v112 = (char *)&v112 + 8;
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v4);
    if ( ActivityIdThread )
    {
      *((_QWORD *)&v112 + 1) = *ActivityIdThread;
      v113 = ActivityIdThread[1];
      *(_QWORD *)&v112 = (char *)&v112 + 8;
    }
    else
    {
      *(_QWORD *)&v112 = 0;
    }
  }
  v7 = v97;
  v115 = *(_OWORD *)(v97 + 8512);
  v107 = *(_QWORD *)(v97 + 8528);
  LODWORD(v95) = *(_DWORD *)(v97 + 8536);
  v106 = (int)v95;
  if ( (*(_DWORD *)(v97 + 24) & 4) != 0 )
    v114 = *(_OWORD *)(v97 + 7824);
  else
    v114 = 0;
  v8 = (int *)(a1 + 12);
  if ( (*(_DWORD *)(a1 + 12) & 0x40000) == 0 )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    if ( NtfsTelemetryGuard(0x200u) )
      NtfsTelemetryDismountBegin(
        (unsigned int)&v112,
        (unsigned int)&v114,
        (unsigned int)&v115,
        (unsigned int)&v107,
        (_DWORD)v95,
        (*v8 & 1) == 0);
    v93 = 1;
  }
  if ( (*v8 & 0x40000) == 0 )
  {
    if ( dword_140092174
      && (unsigned __int8)(byte_140092178 - 1) > 2u
      && (qword_140092160 & 0x8000000) != 0
      && (qword_140092168 & 0x8000000) == qword_140092168
      && (*(_DWORD *)(a1 + 16) & 0x100000) == 0 )
    {
      v9 = *(_QWORD *)(v7 + 248);
      v10 = *(_WORD *)(v9 + 6);
      if ( v10 > 0x40u || (v10 & 1) != 0 )
        v10 = 0;
      *(_DWORD *)(&UnicodeString.MaximumLength + 1) = 0;
      v5 = 0;
      if ( v10 )
        v5 = v9 + 32;
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000000) != 0 )
      {
        v11 = *(unsigned __int16 *)(v7 + 7856) >> 1;
        v83 = *(_QWORD *)(v7 + 7864);
        LODWORD(v82) = v11;
        LODWORD(Timeout) = v10 >> 1;
        McTemplateU0ppww_EtwWriteTransfer(v11, (const EVENT_DESCRIPTOR *)fsctrl_c3971, a1, v7, Timeout, v5, v82, v83);
      }
    }
    NtfsSendBeginDismountEvent(a1, v7, v5, 0);
  }
  if ( !v101 || (v101->CurrentByteOffset.LowPart & 0x200) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      if ( v101 )
        LowPart_low = LOWORD(v101->CurrentByteOffset.LowPart);
      else
        LowPart_low = 0;
      v75 = *(_QWORD *)(v7 + 248);
      v76 = *(_WORD *)(v75 + 6);
      if ( v76 > 0x40u || (v76 & 1) != 0 )
        v76 = 0;
      v77 = v76 >> 1;
      v78 = *(unsigned __int16 *)(v7 + 7872) >> 1;
      LODWORD(v84) = LowPart_low;
      v83 = v75 + 32;
      LODWORD(v82) = v77;
      v81 = *(_QWORD *)(v7 + 7880);
      LODWORD(Timeout) = v78;
      McTemplateU0ppwwd_EtwWriteTransfer(
        v77,
        (const EVENT_DESCRIPTOR *)fsctrl_c3986,
        KeGetCurrentThread(),
        v7,
        Timeout,
        v81,
        v82,
        v75 + 32,
        v84);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC0000022, 0x120F9Du);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741790, a2 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000022, 0x120F9Eu);
    return 3221225506LL;
  }
  v101 = FileObject;
  v109[0] = (const wchar_t *)(a1 + 12);
  v94 = -1073741823;
  v90 = 0;
  v92 = 0;
  v91 = 0;
  v12 = 1;
  if ( (*v8 & 0x40000) == 0 )
  {
    UnicodeString = 0;
    v89 = 0;
    KeWaitForSingleObject((PVOID)(v7 + 6632), Executive, 0, 0, 0);
    NtfsFillVcbVolumeGuid(a1);
    NtfsRepairGetVolumeId(a1, v7, 0, (__int64)&UnicodeString, &v89);
    v13 = &word_140064400;
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v14 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6736) )
        v14 = *(const wchar_t **)(v7 + 6736);
      v15 = (*(_DWORD *)(v7 + 28) >> 2) & 1;
      v16 = *(_DWORD *)(v7 + 6660);
      if ( (unsigned int)(v16 - 1) > 0x13 )
        LOBYTE(v16) = 0;
      v17 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6720) )
        v17 = *(const wchar_t **)(v7 + 6720);
      v102 = v17;
      v18 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6704) )
        v18 = *(const wchar_t **)(v7 + 6704);
      v95 = v18;
      v19 = (unsigned int *)&word_140064400;
      if ( *(_QWORD *)(v7 + 6688) )
        v19 = *(unsigned int **)(v7 + 6688);
      v98 = (wchar_t *)v19;
      v20 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6672) )
        v20 = *(const wchar_t **)(v7 + 6672);
      v99 = v20;
      v21 = &word_140064400;
      if ( *(_QWORD *)(v7 + 7864) )
        v21 = *(const wchar_t **)(v7 + 7864);
      v104[0] = v21;
      if ( (*(_DWORD *)(v7 + 4) & 0xC00) != 0x800
        && (v22 = *(_QWORD *)(v7 + 248)) != 0
        && (v23 = *(_QWORD *)(v22 + 16)) != 0 )
      {
        v24 = (*(_DWORD *)(v23 + 48) >> 8) & 1;
      }
      else
      {
        v24 = 0;
      }
      McTemplateK0jmztzzzzzqjqtz_EtwWriteTransfer(
        v7 + 7808,
        v24,
        (const GUID *)v112,
        v7 + 7824,
        v7 + 8528,
        UnicodeString.Buffer,
        v24,
        v104[0],
        v99,
        v98,
        v95,
        v102,
        v16,
        v7 + 7808,
        *(_DWORD *)(v7 + 6792),
        v15,
        v14);
    }
    v25 = KeQueryUnbiasedInterruptTime();
    FsRtlNotifyVolumeEvent(FileObject, 1u);
    v26 = (KeQueryUnbiasedInterruptTime() - v25) / 0xA / 0x3E8;
    IoPerfPrintTimeInterval(v26, 2u, &v116);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v27 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6736) )
        v27 = *(const wchar_t **)(v7 + 6736);
      v104[0] = v27;
      v28 = (*(_DWORD *)(v7 + 28) >> 2) & 1;
      v29 = *(_DWORD *)(v7 + 6660);
      if ( (unsigned int)(v29 - 1) > 0x13 )
        LOBYTE(v29) = 0;
      v30 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6720) )
        v30 = *(const wchar_t **)(v7 + 6720);
      v99 = v30;
      v31 = (unsigned int *)&word_140064400;
      if ( *(_QWORD *)(v7 + 6704) )
        v31 = *(unsigned int **)(v7 + 6704);
      v98 = (wchar_t *)v31;
      v32 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6688) )
        v32 = *(const wchar_t **)(v7 + 6688);
      v102 = v32;
      v33 = &word_140064400;
      if ( *(_QWORD *)(v7 + 6672) )
        v33 = *(const wchar_t **)(v7 + 6672);
      v95 = v33;
      if ( *(_QWORD *)(v7 + 7864) )
        v13 = *(const wchar_t **)(v7 + 7864);
      if ( (*(_DWORD *)(v7 + 4) & 0xC00) != 0x800
        && (v34 = *(_QWORD *)(v7 + 248)) != 0
        && (v35 = *(_QWORD *)(v34 + 16)) != 0 )
      {
        v36 = (*(_DWORD *)(v35 + 48) >> 8) & 1;
      }
      else
      {
        v36 = 0;
      }
      McTemplateK0jmztzzzzzqjqtzzx_EtwWriteTransfer(
        v7 + 7808,
        v36,
        (const GUID *)v112,
        v7 + 7824,
        v7 + 8528,
        UnicodeString.Buffer,
        v36,
        v13,
        v95,
        v102,
        v98,
        v99,
        v29,
        v7 + 7808,
        *(_DWORD *)(v7 + 6792),
        v28,
        v104[0],
        &v116,
        v26);
    }
    if ( v89 )
      RtlFreeUnicodeString(&UnicodeString);
    v12 = 1;
  }
  while ( 1 )
  {
    NtfsPurgeFileRecordCache(a1);
    NtfsAcquireCheckpointSynchronization(a1, v7, 80);
    v91 = 1;
    NtfsAcquireExclusiveVcb(a1, v7, 1);
    v90 = 1;
    if ( *(_DWORD *)(v7 + 280) )
    {
      v46 = *(_DWORD *)(v7 + 4);
      if ( (v46 & 2) != 0 )
      {
        v51 = *(_DWORD *)(v7 + 260);
        v52 = *(_DWORD *)(v7 + 268);
        v53 = *(_DWORD *)(v7 + 264);
        if ( v53 == v51 + ~v52 )
        {
          if ( NtfsStatusDebugFlags )
          {
            v39 = 1183785;
LABEL_118:
            NtfsStatusTraceAndDebugInternal(0, 0xC00004BD, v39);
          }
LABEL_119:
          v94 = -1073740611;
          goto LABEL_131;
        }
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v54 = *(_QWORD *)(v7 + 248);
          v55 = *(unsigned __int16 *)(v54 + 6);
          if ( v55 > 0x40 || (v55 & 1) != 0 )
            v55 = 0;
          LODWORD(FileObject) = v55;
          LOWORD(v104[0]) = v55;
          v104[1] = (const wchar_t *)(v54 + 32);
          v56 = *(unsigned __int16 *)(v7 + 7872) >> 1;
          LODWORD(v87) = v52;
          LODWORD(v86) = v51;
          LODWORD(v85) = v53;
          LODWORD(v84) = v46;
          v83 = v54 + 32;
          LODWORD(v82) = (unsigned __int16)v55 >> 1;
          v81 = *(_QWORD *)(v7 + 7880);
          LODWORD(Timeout) = v56;
          McTemplateU0ppwwdddd_EtwWriteTransfer(
            v56,
            (const EVENT_DESCRIPTOR *)fsctrl_c4145,
            KeGetCurrentThread(),
            v7,
            Timeout,
            v81,
            v82,
            v54 + 32,
            v84,
            v85,
            v86,
            v87);
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_130;
        v50 = 1183807;
      }
      else
      {
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v47 = *(_QWORD *)(v7 + 248);
          v48 = *(unsigned __int16 *)(v47 + 6);
          if ( v48 > 0x40 || (v48 & 1) != 0 )
            v48 = 0;
          LODWORD(v102) = v48;
          LOWORD(v109[0]) = v48;
          v109[1] = (const wchar_t *)(v47 + 32);
          v49 = *(unsigned __int16 *)(v7 + 7872) >> 1;
          LODWORD(v84) = v46;
          v83 = v47 + 32;
          LODWORD(v82) = (unsigned __int16)v48 >> 1;
          v81 = *(_QWORD *)(v7 + 7880);
          LODWORD(Timeout) = v49;
          McTemplateU0ppwwd_EtwWriteTransfer(
            v49,
            (const EVENT_DESCRIPTOR *)fsctrl_c4117,
            KeGetCurrentThread(),
            v7,
            Timeout,
            v81,
            v82,
            v47 + 32,
            v84);
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_130;
        v50 = 1183776;
      }
      NtfsStatusTraceAndDebugInternal(0, 0xC0000022, v50);
LABEL_130:
      v94 = -1073741790;
      goto LABEL_131;
    }
    v92 = 1;
    v37 = *(_DWORD *)(v7 + 4);
    if ( (v37 & 1) == 0 )
      break;
    if ( NtfsIsDismountProtectedStateSepVolume(a1, *(_QWORD *)(v7 + 224)) )
    {
      if ( NtfsStatusDebugFlags )
      {
        v39 = 1183847;
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    v104[0] = (const wchar_t *)(v7 + 4);
    v98 = (wchar_t *)(v7 + 4);
    if ( !v12 )
    {
      v99 = (const wchar_t *)(v7 + 5521);
      if ( !*(_BYTE *)(v7 + 5521) && NtfsFlushTrimRequestsOnDismount )
        NtfsFlushAllTrimHintsSynchronous(a1, v7, v38);
      *(_BYTE *)(v7 + 5521) = 1;
      v42 = *v8;
      if ( (*v8 & 0x40000) == 0 && (*(_DWORD *)(v7 + 4) & 0x2000000) == 0 )
      {
        *(_DWORD *)(a1 + 392) = 8;
        *v8 = v42 | 0x40000;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC0000188, 0x1210CFu);
        NtfsRaiseStatusInternal(a1, -1073741432, 0, 0, 1183951);
      }
      if ( (*(_DWORD *)(v7 + 24) & 0x40000) != 0 )
      {
        KeClearEvent(*(PRKEVENT *)(v7 + 1432));
        v43 = NtfsFlushVolume((_DWORD *)a1, v7, 0x447u);
        v94 = v43;
        if ( (*(_DWORD *)(v7 + 24) & 0x40000) != 0
          && ((v45 = *(_QWORD *)(v7 + 64)) == 0 || (*(_DWORD *)(v45 + 200) & 0x20000) != 0)
          || v43 != -1073741797 && !NtfsAreClustersDangling(a1, v7, v44) )
        {
          NtfsFlushVolume((_DWORD *)a1, v7, 0x8Fu);
          KeSetEvent(*(PRKEVENT *)(v7 + 1432), 0, 0);
          goto LABEL_103;
        }
        NtfsFlushVolume((_DWORD *)a1, v7, 0x80u);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC000049C, 0x121114u);
        v94 = -1073740644;
        local_unwind_0((__int64)v111, (__int64)&loc_14029EA45);
      }
      NtfsFlushVolume((_DWORD *)a1, v7, 0xFu);
LABEL_103:
      NtfsPerformDismountOnVcb((char *)a1, v7, 0, 0, 0, 0);
      SetFlagInterlocked((unsigned int *)v98, 2u);
      *(_QWORD *)(v7 + 1472) = (char *)&FileObject->Type + 1;
      NtfsSetDirectWritesAllowed(*(_QWORD *)(v7 + 248));
LABEL_104:
      v94 = 0;
      goto LABEL_131;
    }
    NtfsReleaseVcb(a1, v7);
    v90 = 0;
    NtfsReleaseCheckpointSynchronization(v40, v7, 16);
    v91 = 0;
    TxfShutdownVolume(a1, v7, 0, v41, 0);
    v12 = 0;
  }
  if ( (v37 & 0x800000) == 0 )
    goto LABEL_104;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC000026E, 0x121059u);
  v94 = -1073741202;
LABEL_131:
  v57 = v94;
  if ( v94 || !v92 )
  {
    v58 = v97;
  }
  else
  {
    v58 = v97;
    SetFlagInterlocked((unsigned int *)(v97 + 4), 0x800000u);
  }
  FsRtlDismountComplete(*(_QWORD *)(v58 + 224), (unsigned int)v57);
  NtfsReleaseCheckpointSynchronization(v59, v58, 16);
  v60 = v96;
  if ( v57 < 0 )
    NtfsUpdateDeleteNotificationVolumeSetting(v96, v58);
  NtfsReleaseVcb(v60, v58);
  if ( (int)(v57 + 0x80000000) >= 0 && v57 != -1073741202 )
  {
    v108 = 0;
    v89 = 0;
    NtfsFillVcbVolumeGuid(v60);
    NtfsRepairGetVolumeId(v60, *(_QWORD *)(v60 + 104), 1, (__int64)&v108, &v89);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x80000) != 0 )
    {
      v61 = &word_140064400;
      v62 = &word_140064400;
      if ( *(_QWORD *)(v58 + 6736) )
        v62 = *(const wchar_t **)(v58 + 6736);
      v63 = (*(_DWORD *)(v58 + 28) >> 2) & 1;
      v64 = *(_DWORD *)(v58 + 6660);
      if ( (unsigned int)(v64 - 1) > 0x13 )
        LOBYTE(v64) = 0;
      v65 = &word_140064400;
      if ( *(_QWORD *)(v58 + 6720) )
        v65 = *(const wchar_t **)(v58 + 6720);
      v109[0] = v65;
      v66 = &word_140064400;
      if ( *(_QWORD *)(v58 + 6704) )
        v66 = *(const wchar_t **)(v58 + 6704);
      v104[0] = v66;
      v67 = &word_140064400;
      if ( *(_QWORD *)(v58 + 6688) )
        v67 = *(const wchar_t **)(v58 + 6688);
      v99 = v67;
      v68 = (unsigned int *)&word_140064400;
      if ( *(_QWORD *)(v58 + 6672) )
        v68 = *(unsigned int **)(v58 + 6672);
      v98 = (wchar_t *)v68;
      if ( *(_QWORD *)(v58 + 7864) )
        v61 = *(const wchar_t **)(v58 + 7864);
      if ( (*(_DWORD *)(v58 + 4) & 0xC00) != 0x800
        && (v69 = *(_QWORD *)(v58 + 248)) != 0
        && (v70 = *(_QWORD *)(v69 + 16)) != 0 )
      {
        v71 = (*(_DWORD *)(v70 + 48) >> 8) & 1;
      }
      else
      {
        LOBYTE(v71) = 0;
      }
      McTemplateK0jmztzzzzzqjqtzpd_EtwWriteTransfer(
        v58 + 7808,
        v58 + 8528,
        (const GUID *)v112,
        v58 + 7824,
        v58 + 8528,
        v108.Buffer,
        v71,
        v61,
        v98,
        v99,
        v104[0],
        v109[0],
        v64,
        v58 + 7808,
        *(_DWORD *)(v58 + 6792),
        v63,
        v62,
        v88,
        v57);
    }
    if ( v89 )
      RtlFreeUnicodeString(&v108);
    FsRtlNotifyVolumeEvent(v101, 2u);
  }
  if ( v93 )
  {
    v72 = KeQueryUnbiasedInterruptTime();
    if ( NtfsTelemetryGuard(0x200u) )
      NtfsTelemetryDismountEnd(
        (__int128 **)&v112,
        (__int64)&v114,
        (__int64)&v115,
        (__int64)&v107,
        v106,
        v57,
        v72 - UnbiasedInterruptTime);
  }
  if ( NtfsStatusDebugFlags && v57 && (unsigned int)(v57 - 298) > 1 && (unsigned int)(v57 + 2147483643) > 1 )
    NtfsStatusTraceAndDebugInternal(v60, v57, 0x1211C0u);
  NtfsExtendedCompleteRequestInternal(v60, v110, v57, v110 != 0, v57 >= 0);
  return (unsigned int)v57;
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
