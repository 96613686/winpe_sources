# NtfsFreeRecentlyDeallocated

- ea: `0x14020f350`
- end: `0x140210bb8`
- name: `NtfsFreeRecentlyDeallocated`
- size: `6248`
- prototype: `void __fastcall(int *, __int64, _QWORD *, unsigned __int8)`
- caller_count: `5`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400450dc`
- `0x1400cc78c`
- `0x1401cfc18`
- `0x14021ebd0`
- `0x14027e3c8`

## callees

- `0x14000549c`
- `0x140007670`
- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x140030a80`
- `0x14003b914`
- `0x14003c184`
- `0x14003c34c`
- `0x14003fae0`
- `0x14004062c`
- `0x140040d48`
- `0x14004a850`
- `0x14004c748`
- `0x140059250`
- `0x1400596c0`
- `0x1400b75cc`
- `0x14012e4f0`
- `0x14016aa30`
- `0x1401cf24c`
- `0x14020f350`
- `0x1402143b0`
- `0x1402434fc`
- `0x14027747c`
- `0x140292d10`
- `0x14029a9b0`
- `0x14029aa5c`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x14020fd47`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14020fd47`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x14020f6a3`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x1402104e3`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x1402b4500`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x14020f6a3`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x1402104e3`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x1402b4500`
- `ntoskrnl!IofCompleteRequest` at `0x140210b4d`
- `ntoskrnl!IofCompleteRequest` at `0x140210b4d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020ff36`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020ff36`
- `ntoskrnl!RtlFindFirstRunClear` at `0x140210153`
- `ntoskrnl!RtlFindFirstRunClear` at `0x140210153`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x1402107fd`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x1402b47a5`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x1402107fd`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x1402b47a5`
- `ntoskrnl!FsRtlNumberOfRunsInBaseMcb` at `0x140210863`
- `ntoskrnl!FsRtlNumberOfRunsInBaseMcb` at `0x140210863`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b43ce`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b481e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b43ce`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b481e`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140210516`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402b452b`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140210516`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402b452b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402107e8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b478c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402107e8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b478c`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402107d2`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b4776`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402107d2`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b4776`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140210910`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140210910`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402108d5`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402108d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020ffb3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020ffb3`
- `ntoskrnl!KeInitializeEvent` at `0x14020feec`
- `ntoskrnl!KeInitializeEvent` at `0x14020feec`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x14021026f`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x14021026f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402105f4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140210784`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4624`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4734`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402105f4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140210784`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4624`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4734`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020fdf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210a95`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b488e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020fdf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210a95`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b488e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14020fe36`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14020fe36`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14021054e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402106d9`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b456d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b4676`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14021054e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402106d9`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b456d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b4676`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14021064c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140210697`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14021064c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140210697`

## pseudocode

```c
void __fastcall NtfsFreeRecentlyDeallocated(int *a1, __int64 a2, _QWORD *a3, unsigned __int8 a4)
{
  __int64 v5; // r15
  _QWORD *v6; // rdi
  __int64 v7; // rdx
  __int64 *v8; // rdx
  char *v9; // rdi
  _QWORD *v10; // rcx
  _DWORD *v11; // rbx
  int v12; // r8d
  __int64 v13; // r8
  __int64 *v14; // rdx
  __int64 v15; // rdi
  int v16; // r12d
  __int64 v17; // rcx
  ULONG i; // r12d
  __int64 v19; // rdi
  __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // rcx
  int appended; // eax
  PVOID *v24; // rbx
  PVOID *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned __int64 v28; // r9
  __int64 v29; // r10
  unsigned __int64 v30; // rdx
  PVOID *v31; // rcx
  unsigned __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // r9
  __int64 v35; // r11
  unsigned __int64 v36; // rax
  PVOID *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // r8
  __int64 v41; // r9
  char *v42; // rbx
  int v43; // eax
  __int64 v44; // rcx
  __int64 *v45; // rdx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rdx
  PVOID *v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rax
  unsigned __int64 v51; // r9
  __int64 v52; // r10
  unsigned __int64 v53; // rdx
  BOOLEAN v54; // al
  ULONG OutputBufferLength; // ebx
  int *PoolWithTag; // rdi
  unsigned int v57; // eax
  size_t v58; // r8
  __int64 v59; // rcx
  struct _DEVICE_OBJECT *v60; // rsi
  PIRP v61; // rax
  IRP *v62; // rdi
  int v63; // eax
  __int64 v64; // rcx
  unsigned int v65; // ebx
  NTSTATUS Status; // ebx
  bool v67; // di
  char v68; // si
  ULONG FirstRunClear; // eax
  __int64 v70; // rcx
  ULONG NextForwardRunClear; // ebx
  unsigned __int64 v72; // r8
  __int64 v73; // rdx
  char v74; // r9
  ULONG v75; // eax
  char *v76; // rsi
  PVOID v77; // rdx
  PVOID v78; // rdx
  ULONG v79; // ebx
  char *v80; // rdi
  _QWORD *v81; // rbx
  LONGLONG v82; // rcx
  __int64 v83; // rcx
  signed __int64 v84; // rdx
  __int64 v85; // r8
  signed __int64 v86; // rcx
  signed __int64 v87; // rax
  signed __int64 v88; // rcx
  signed __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rcx
  signed __int64 v93; // rdx
  __int64 v94; // r8
  signed __int64 v95; // rcx
  signed __int64 v96; // rax
  signed __int64 v97; // rcx
  signed __int64 v98; // rax
  _QWORD *v99; // rcx
  PVOID *v100; // rax
  int v101; // eax
  char *v102; // rbx
  char *v103; // rax
  __int64 v104; // rcx
  _QWORD *v105; // rax
  __int64 v106; // rcx
  PLONGLONG SectorCount; // [rsp+88h] [rbp-238h]
  PLONGLONG SectorCounta; // [rsp+88h] [rbp-238h]
  BOOLEAN InternalDeviceIoControl[8]; // [rsp+98h] [rbp-228h]
  char v110; // [rsp+B8h] [rbp-208h]
  char v111; // [rsp+B9h] [rbp-207h]
  char v112; // [rsp+BAh] [rbp-206h]
  char v113; // [rsp+BBh] [rbp-205h]
  _BYTE v114[4]; // [rsp+BCh] [rbp-204h] BYREF
  int v115; // [rsp+C0h] [rbp-200h]
  __int64 v116; // [rsp+C8h] [rbp-1F8h] BYREF
  PVOID v117; // [rsp+D0h] [rbp-1F0h]
  ULONG StartingIndex; // [rsp+D8h] [rbp-1E8h] BYREF
  bool v119; // [rsp+DCh] [rbp-1E4h]
  ULONG v120; // [rsp+E0h] [rbp-1E0h]
  __int64 Lbn; // [rsp+E8h] [rbp-1D8h] BYREF
  PVOID v122[2]; // [rsp+F0h] [rbp-1D0h] BYREF
  int v123; // [rsp+100h] [rbp-1C0h]
  PVOID Entry[2]; // [rsp+108h] [rbp-1B8h] BYREF
  int v125; // [rsp+118h] [rbp-1A8h] BYREF
  PVOID v126; // [rsp+120h] [rbp-1A0h] BYREF
  LONGLONG v127[3]; // [rsp+128h] [rbp-198h] BYREF
  ULONG v128; // [rsp+140h] [rbp-180h]
  ULONG v129; // [rsp+144h] [rbp-17Ch]
  PVOID P; // [rsp+148h] [rbp-178h]
  char *v131; // [rsp+150h] [rbp-170h]
  LONGLONG v132; // [rsp+158h] [rbp-168h] BYREF
  __int64 v133; // [rsp+160h] [rbp-160h] BYREF
  NTSTATUS v134; // [rsp+168h] [rbp-158h] BYREF
  char *v135; // [rsp+170h] [rbp-150h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+178h] [rbp-148h] BYREF
  PVOID *v137; // [rsp+188h] [rbp-138h]
  PVOID *v138; // [rsp+190h] [rbp-130h]
  unsigned __int64 v139; // [rsp+198h] [rbp-128h]
  _QWORD *v140; // [rsp+1A0h] [rbp-120h]
  __int64 Vbn; // [rsp+1A8h] [rbp-118h] BYREF
  _DWORD *v142; // [rsp+1B0h] [rbp-110h]
  __int64 v143; // [rsp+1B8h] [rbp-108h]
  PVOID *v144; // [rsp+1C0h] [rbp-100h]
  PVOID *v145; // [rsp+1C8h] [rbp-F8h]
  __int64 v146; // [rsp+1D0h] [rbp-F0h]
  PVOID *v147; // [rsp+1D8h] [rbp-E8h]
  PVOID *v148; // [rsp+1E0h] [rbp-E0h]
  __int64 v149; // [rsp+1E8h] [rbp-D8h]
  PVOID *v150; // [rsp+1F0h] [rbp-D0h]
  PVOID *v151; // [rsp+1F8h] [rbp-C8h]
  __int64 v152; // [rsp+200h] [rbp-C0h]
  _QWORD *v153; // [rsp+208h] [rbp-B8h]
  char *v154; // [rsp+218h] [rbp-A8h]
  char *v155; // [rsp+220h] [rbp-A0h]
  char *v156; // [rsp+228h] [rbp-98h]
  char *v157; // [rsp+230h] [rbp-90h]
  ULONG v158; // [rsp+238h] [rbp-88h]
  struct _KEVENT Event; // [rsp+240h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+258h] [rbp-68h] BYREF
  __int128 InputBuffer; // [rsp+268h] [rbp-58h] BYREF

  v5 = (__int64)a1;
  v140 = a3;
  v127[2] = (LONGLONG)a1;
  v127[1] = a2;
  v125 = 0;
  *(_OWORD *)Entry = 0;
  *(_OWORD *)v122 = 0;
  if ( (!a1 || (a1[4] & 0x100000LL) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
  {
    McTemplateU0piq_EtwWriteTransfer((__int64)a1, a2, a2, *a3, a4);
  }
  v6 = (_QWORD *)(a2 + 1608);
  if ( (_QWORD *)*v6 == v6 || (v7 = *(_QWORD *)(a2 + 72)) == 0 )
  {
    if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
    {
      v8 = logsup_c7211;
      goto LABEL_301;
    }
    return;
  }
  v143 = a2;
  v153 = (_QWORD *)(a2 + 1608);
  NtfsAcquireExclusiveScbEx(v5, v7, 0);
  if ( (_QWORD *)*v6 == v6 )
  {
    NtfsReleaseFcbEx(v5, *(_QWORD *)(*(_QWORD *)(a2 + 72) + 184LL), 0);
    if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
    {
      v8 = logsup_c7231;
LABEL_301:
      McTemplateU0p_EtwWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)v8, a2);
      return;
    }
    return;
  }
  v128 = 0;
  P = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v155 = (char *)(a2 + 1608);
  v154 = (char *)(a2 + 1608);
  v110 = *(_BYTE *)(a2 + 5521);
  v114[1] = v110;
  v9 = *(char **)(a2 + 1616);
  v117 = v9;
  v131 = v9;
  while ( 1 )
  {
LABEL_13:
    v10 = v153;
    if ( (_QWORD *)*v10 == v10 )
      goto LABEL_31;
    if ( v111 )
      goto LABEL_288;
    v11 = v9 + 56;
    v142 = v9 + 56;
    v12 = *((_DWORD *)v9 + 14);
    if ( (v12 & 1) == 0 && (v12 & 0x30) == 0 )
    {
      v10 = (_QWORD *)*((_QWORD *)v9 + 5);
      if ( (!v10 || *v140 <= (__int64)v10) && !a4 )
        goto LABEL_31;
    }
    if ( (*((_DWORD *)v9 + 14) & 1) == 0 )
      break;
    if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0pp_EtwWriteTransfer((__int64)v10, (const EVENT_DESCRIPTOR *)logsup_c7283, a2, *((_QWORD *)v9 + 6));
    }
    v9 = (char *)*((_QWORD *)v9 + 1);
    v117 = v9;
    v131 = v9;
    if ( v9 == v154 )
    {
      if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
      {
        v13 = a2;
        v14 = logsup_c7298;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
  }
  v157 = v9;
  v156 = v9 + 56;
  if ( v9 != v155 )
  {
    v16 = 0;
    v115 = 0;
    v114[0] = 0;
    v126 = 0;
    v129 = 0;
    Vbn = 0;
    Lbn = 0;
    v116 = 0;
    v17 = *((_QWORD *)v9 + 6);
    if ( v17 <= 0 )
    {
      v42 = (char *)v117;
      goto LABEL_209;
    }
    if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      *(_DWORD *)InternalDeviceIoControl = v12;
      McTemplateU0ppiid_EtwWriteTransfer(
        v17,
        (const EVENT_DESCRIPTOR *)logsup_c7352,
        a2,
        v9,
        v17,
        *((_QWORD *)v9 + 5),
        *(_QWORD *)InternalDeviceIoControl);
    }
    for ( i = 0; ; ++i )
    {
      v129 = i;
      if ( !FsRtlGetNextBaseMcbEntry((PBASE_MCB)(v9 + 16), i, &Vbn, &Lbn, &v116) )
      {
LABEL_203:
        v74 = v110;
        goto LABEL_204;
      }
      v19 = Lbn;
      if ( Vbn == Lbn )
        break;
LABEL_202:
      v9 = (char *)v117;
    }
    v17 = v116;
    v20 = v116;
    if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
    {
      LODWORD(SectorCount) = i;
      McTemplateU0ppdii_EtwWriteTransfer(v116, (const EVENT_DESCRIPTOR *)logsup_c7375, a2, v117, SectorCount, Lbn, v116);
      v17 = v116;
    }
    if ( (*(_DWORD *)(a2 + 24) & 0x40000) != 0 && (*v11 & 0x10) == 0 )
    {
      if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
      {
        McTemplateU0_EtwWriteTransfer(v17, (const EVENT_DESCRIPTOR *)logsup_c7398);
        LODWORD(v17) = v116;
      }
      Entry[1] = Entry;
      Entry[0] = Entry;
      v112 = 1;
      v122[1] = v122;
      v122[0] = v122;
      v113 = 1;
      v21 = FsLibGroupSubExtentsByDanglingMdl(
              *(_QWORD *)(a2 + 224),
              Lbn,
              v17,
              *(_DWORD *)(a2 + 356),
              (__int64)Entry,
              (__int64)v122,
              0);
      v123 = v21;
      if ( v21 < 0 )
      {
        if ( !v5 || (v22 = *(unsigned int *)(v5 + 16), (v22 & 0x100000) == 0) )
        {
          if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
            McTemplateU0q_EtwWriteTransfer(v22, (const EVENT_DESCRIPTOR *)logsup_c7423, v21);
        }
        FsLibUninitializeExtentList((_QWORD **)v122);
        v122[1] = v122;
        v122[0] = v122;
        FsLibUninitializeExtentList((_QWORD **)Entry);
        Entry[1] = Entry;
        Entry[0] = Entry;
        appended = FsLibAppendExtent(Entry, Lbn, v116);
        v123 = appended;
        if ( appended < 0 )
        {
          if ( !v5 || (v17 = *(unsigned int *)(v5 + 16), (v17 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
              McTemplateU0q_EtwWriteTransfer(v17, (const EVENT_DESCRIPTOR *)logsup_c7441, appended);
          }
          v111 = 1;
          goto LABEL_207;
        }
      }
      v116 = 0;
      v24 = (PVOID *)v122[0];
      if ( v122[0] == v122 )
        goto LABEL_108;
      v147 = v122;
      v25 = (PVOID *)v122[0];
      v148 = (PVOID *)v122[0];
      v26 = 0;
      v149 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      while ( !v25[2 * v27 + 4] )
      {
        v47 = *((unsigned int *)v25 + 4);
        if ( v28 >= v47 || (v27 = v29 + 1, v29 + 1 >= v47) )
        {
          v25 = (PVOID *)*v25;
          if ( v25 == v122 )
          {
            v149 = v26 + 1;
            goto LABEL_108;
          }
          v148 = v25;
          v26 = 0;
          v149 = 0;
          v27 = 0;
          v28 = 0;
          v29 = 0;
        }
        else
        {
          v26 = v29 + 1;
          v149 = v29 + 1;
          v28 = ++v29;
        }
      }
      v30 = 0;
      v137 = v122;
      v31 = 0;
      v138 = 0;
      if ( v122[0] != v122 )
      {
        v31 = (PVOID *)v122[0];
        v138 = (PVOID *)v122[0];
        v30 = 0;
        v139 = 0;
        v32 = 0;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        while ( 1 )
        {
          if ( v31[2 * v33 + 4] )
          {
            Lbn = (__int64)v31[2 * v34 + 3];
            v116 = (__int64)v31[2 * v33 + 4];
            break;
          }
          v36 = *((unsigned int *)v31 + 4);
          if ( v32 >= v36 || (v32 = v35 + 1, v35 + 1 >= v36) )
          {
            v37 = (PVOID *)*v31;
            if ( *v31 == v137 )
            {
              v139 = ++v30;
              break;
            }
            v31 = (PVOID *)*v31;
            v138 = v37;
            v30 = 0;
            v32 = 0;
            v33 = 0;
            v34 = 0;
            v35 = 0;
          }
          else
          {
            v30 = v35 + 1;
            v33 = v35 + 1;
            v34 = ++v35;
          }
          v139 = v30;
        }
      }
      if ( v31 && v30 < *((unsigned int *)v31 + 4) )
      {
        v31[2 * v30 + 4] = 0;
        v24 = (PVOID *)v122[0];
      }
      if ( v24 == v122 )
      {
LABEL_108:
        v42 = (char *)v117;
      }
      else
      {
        v144 = v122;
        v145 = v24;
        v38 = 0;
        v146 = 0;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        while ( !v24[2 * v39 + 4] )
        {
          v46 = *((unsigned int *)v24 + 4);
          if ( v40 >= v46 || (v39 = v41 + 1, v41 + 1 >= v46) )
          {
            v24 = (PVOID *)*v24;
            if ( v24 == v122 )
            {
              v146 = v38 + 1;
              goto LABEL_108;
            }
            v145 = v24;
            v38 = 0;
            v146 = 0;
            v39 = 0;
            v40 = 0;
            v41 = 0;
          }
          else
          {
            v38 = v41 + 1;
            v146 = v41 + 1;
            v40 = ++v41;
          }
        }
        v42 = (char *)v117;
        v43 = NtfsAddToMatchingDeallocatedClusters(v5, a2, (unsigned int)v122, (_DWORD)v117, 0, 16);
        v123 = v43;
        if ( v43 < 0 )
        {
          if ( !v5 || (v44 = *(unsigned int *)(v5 + 16), (v44 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
            {
              v45 = logsup_c7500;
              goto LABEL_94;
            }
          }
          goto LABEL_95;
        }
      }
      v48 = (PVOID *)Entry[0];
      if ( Entry[0] == Entry )
      {
LABEL_125:
        if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
        {
          McTemplateU0_EtwWriteTransfer((__int64)v48, (const EVENT_DESCRIPTOR *)logsup_c7574);
        }
      }
      else
      {
        v150 = Entry;
        v151 = (PVOID *)Entry[0];
        v49 = 0;
        v152 = 0;
        v50 = 0;
        v51 = 0;
        v52 = 0;
        while ( !v48[2 * v50 + 4] )
        {
          v53 = *((unsigned int *)v48 + 4);
          if ( v51 >= v53 || (v50 = v52 + 1, v52 + 1 >= v53) )
          {
            v48 = (PVOID *)*v48;
            if ( v48 == Entry )
            {
              v152 = v49 + 1;
              goto LABEL_125;
            }
            v151 = v48;
            v49 = 0;
            v152 = 0;
            v50 = 0;
            v51 = 0;
            v52 = 0;
          }
          else
          {
            v49 = v52 + 1;
            v152 = v52 + 1;
            v51 = ++v52;
          }
        }
        if ( (*((_DWORD *)v42 + 14) & 0x20) == 0 )
          _InterlockedIncrement64((volatile signed __int64 *)(a2 + 8792));
        v43 = NtfsAddToMatchingDeallocatedClusters(v5, a2, (unsigned int)Entry, (_DWORD)v42, 1, 32);
        v123 = v43;
        if ( v43 < 0 )
        {
          if ( !v5 || (v44 = *(unsigned int *)(v5 + 16), (v44 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
            {
              v45 = logsup_c7551;
LABEL_94:
              McTemplateU0q_EtwWriteTransfer(v44, (const EVENT_DESCRIPTOR *)v45, v43);
            }
          }
LABEL_95:
          NtfsRemoveExtentFromClustersVerifiedForDangling(v44, a2, v42, v19, v20);
          v111 = 1;
          goto LABEL_208;
        }
      }
      FsLibUninitializeExtentList((_QWORD **)Entry);
      v112 = 0;
      FsLibUninitializeExtentList((_QWORD **)v122);
      v113 = 0;
      v17 = v116;
    }
    if ( (*(_DWORD *)(a2 + 5524) & 1) == 0
      || (v54 = KeAreAllApcsDisabled(), v17 = v116, v54)
      || (unsigned __int64)(v116 - 1) > 0xFFFFFFFE )
    {
LABEL_197:
      if ( v17 )
      {
        if ( v110 )
        {
          if ( !NtfsAddCachedRun(v5, a2, Lbn, v17, 2, 1) )
            goto LABEL_203;
        }
        else
        {
          NtfsSendUnusedClustersHint(v5, Lbn, (unsigned int)v17, &v126, v114);
        }
      }
      ++v115;
      v11 = v142;
      goto LABEL_202;
    }
    InputBuffer = 0;
    OutputBufferLength = 4 * ((8 * (unsigned int)((unsigned __int64)v116 >> 3) + 39) >> 5);
    v158 = OutputBufferLength;
    LODWORD(InputBuffer) = *(_DWORD *)(a2 + 356);
    DWORD1(InputBuffer) = v116;
    *((_QWORD *)&InputBuffer + 1) = Lbn;
    PoolWithTag = (int *)P;
    if ( P )
    {
      v57 = v128;
      if ( v128 >= OutputBufferLength )
      {
LABEL_140:
        if ( !PoolWithTag )
          goto LABEL_197;
        v58 = v57;
        if ( v57 <= 4 )
          v58 = 4;
        memset(PoolWithTag, 0, v58);
        if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          LODWORD(SectorCount) = v116;
          McTemplateU0ppd_EtwWriteTransfer(v59, (const EVENT_DESCRIPTOR *)logsup_c7675, a2, Lbn, SectorCount);
        }
        v60 = *(struct _DEVICE_OBJECT **)(a2 + 224);
        memset(&Event, 0, sizeof(Event));
        IoStatusBlock = 0;
        v134 = 0;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v61 = IoBuildDeviceIoControlRequest(
                0x564052u,
                v60,
                &InputBuffer,
                0x10u,
                PoolWithTag,
                OutputBufferLength,
                0,
                &Event,
                &IoStatusBlock);
        v62 = v61;
        if ( !v61 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, 0xC000009A, 0x121390u);
          NtfsRaiseStatusInternal(v5, -1073741670, 0, 0, 1184656);
        }
        v61->Tail.Overlay.CurrentStackLocation[-1].Flags = v61->Tail.Overlay.CurrentStackLocation[-1].Flags;
        v63 = NtfsCallStorageDriver(v5, v60, v61, *(_QWORD *)(v5 + 104), 0, 0, (unsigned int *)&v134);
        v65 = v63;
        if ( v63 < 0 )
        {
          v62->IoStatus.Status = v63;
          IofCompleteRequest(v62, 1);
          if ( NtfsStatusDebugFlags
            && v65 < 0xFFFFFFED
            && v65 != -1073741802
            && v65 + 2147483643 > 1
            && v65 != -1073741807
            && v65 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(v5, v65, 0x1213ADu);
          }
          NtfsRaiseStatusInternal(v5, v65, 0, 0, 1184685);
        }
        Status = v134;
        if ( v134 == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          Status = IoStatusBlock.Status;
        }
        if ( Status
          && NtfsStatusDebugFlags
          && (((Status - 294) & 0xFFFFFFFA) != 0 || Status == 295)
          && (unsigned int)Status < 0xFFFFFFED
          && Status != -1073741802
          && (unsigned int)(Status + 2147483643) > 1
          && Status != -1073741807
          && Status != 259
          && Status != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(v5, Status, 0x1213BFu);
        }
        v123 = Status;
        if ( Status >= 0 )
        {
          *(&BitMapHeader.SizeOfBitMap + 1) = 0;
          StartingIndex = 0;
          v67 = 0;
          v119 = 0;
          v68 = 0;
          v114[0] = 0;
          BitMapHeader.SizeOfBitMap = v116;
          BitMapHeader.Buffer = (PULONG)P;
          FirstRunClear = RtlFindFirstRunClear(&BitMapHeader, &StartingIndex);
          NextForwardRunClear = FirstRunClear;
          if ( !v5 || (v70 = *(unsigned int *)(v5 + 16), (v70 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
            {
              LODWORD(SectorCounta) = FirstRunClear;
              McTemplateU0ppd_EtwWriteTransfer(
                v70,
                (const EVENT_DESCRIPTOR *)logsup_c7731,
                a2,
                Lbn + StartingIndex,
                SectorCounta);
            }
          }
          v72 = v116;
          v73 = StartingIndex;
          v74 = v110;
          while ( 1 )
          {
            if ( !NextForwardRunClear )
            {
LABEL_185:
              v17 = 0;
              v116 = 0;
              if ( v74 )
              {
                if ( !v67 )
                  goto LABEL_197;
              }
              else if ( !v68 )
              {
                goto LABEL_197;
              }
LABEL_204:
              if ( !v74 )
                NtfsSendUnusedClustersHint(v5, 0, 0, &v126, v114);
LABEL_207:
              v42 = (char *)v117;
LABEL_208:
              v16 = v115;
LABEL_209:
              v76 = (char *)*((_QWORD *)v42 + 1);
              if ( v126 )
              {
                if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000LL) == 0)
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
                {
                  McTemplateU0pp_EtwWriteTransfer(v17, (const EVENT_DESCRIPTOR *)logsup_c7934, a2, v126);
                }
                NtfsFreeMarkUnusedContext(v126);
                v126 = 0;
              }
              if ( v112 )
              {
                while ( 1 )
                {
                  v77 = Entry[0];
                  if ( Entry[0] == Entry )
                    break;
                  if ( *((PVOID **)Entry[0] + 1) != Entry )
                    goto LABEL_267;
                  v90 = *(_QWORD *)Entry[0];
                  if ( *(PVOID *)(*(_QWORD *)Entry[0] + 8LL) != Entry[0] )
                    goto LABEL_267;
                  Entry[0] = *(PVOID *)Entry[0];
                  *(_QWORD *)(v90 + 8) = Entry;
                  ExFreeToPagedLookasideList(&FsLibExtentArrayLookasideList, v77);
                }
                v112 = 0;
              }
              if ( v113 )
              {
                while ( 1 )
                {
                  v78 = v122[0];
                  if ( v122[0] == v122 )
                    break;
                  if ( *((PVOID **)v122[0] + 1) != v122 )
                    goto LABEL_267;
                  v91 = *(_QWORD *)v122[0];
                  if ( *(PVOID *)(*(_QWORD *)v122[0] + 8LL) != v122[0] )
                    goto LABEL_267;
                  v122[0] = *(PVOID *)v122[0];
                  *(_QWORD *)(v91 + 8) = v122;
                  ExFreeToPagedLookasideList(&FsLibExtentArrayLookasideList, v78);
                }
                v113 = 0;
              }
              if ( v111 )
              {
                v132 = 0;
                v133 = 0;
                v127[0] = 0;
                v79 = 0;
                v120 = 0;
                v80 = v157;
                do
                {
                  FsRtlGetNextBaseMcbEntry((PBASE_MCB)(v80 + 16), v79, &v132, &v133, v127);
                  if ( v132 == v133 )
                  {
                    v81 = v117;
                    FsRtlRemoveBaseMcbEntry((PBASE_MCB)((char *)v117 + 16), v132, v127[0]);
                    v82 = v127[0];
                    *(_QWORD *)(a2 + 312) -= v127[0];
                    v81[6] -= v82;
                    if ( (v81[7] & 0x20) != 0 )
                    {
                      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                      *(_QWORD *)(a2 + 328) -= v127[0];
                      v83 = *(_QWORD *)(a2 + 328);
                      if ( v83 < *(_QWORD *)(a2 + 8312) )
                        *(_QWORD *)(a2 + 8312) = v83;
                      v84 = *(_QWORD *)(a2 + 304) - (v83 >> 8) - *(_QWORD *)(a2 + 6368) - v83;
                      if ( v84 <= 0 )
                        v84 = 0;
                      v85 = v143;
                      do
                      {
                        v86 = *(_QWORD *)(v85 + 8344);
                        v87 = v86;
                        if ( v84 < v86 )
                          v87 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8344), v84, v86);
                      }
                      while ( v87 != v86 );
                      do
                      {
                        v88 = *(_QWORD *)(v85 + 8352);
                        v89 = v88;
                        if ( v84 > v88 )
                          v89 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8352), v84, v88);
                      }
                      while ( v89 != v88 );
                      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                    }
                    v115 = --v16;
                    v79 = 1;
                  }
                  else
                  {
                    ++v79;
                  }
                  v120 = v79;
                }
                while ( v16 > 0 );
              }
              else
              {
                *(_QWORD *)(a2 + 312) -= *((_QWORD *)v42 + 6);
                if ( (*((_DWORD *)v42 + 14) & 0x20) != 0 )
                {
                  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                  *(_QWORD *)(a2 + 328) -= *((_QWORD *)v117 + 6);
                  v92 = *(_QWORD *)(a2 + 328);
                  if ( v92 < *(_QWORD *)(a2 + 8312) )
                    *(_QWORD *)(a2 + 8312) = v92;
                  v93 = *(_QWORD *)(a2 + 304) - (v92 >> 8) - *(_QWORD *)(a2 + 6368) - v92;
                  if ( v93 <= 0 )
                    v93 = 0;
                  v94 = v143;
                  do
                  {
                    v95 = *(_QWORD *)(v94 + 8344);
                    v96 = v95;
                    if ( v93 < v95 )
                      v96 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8344), v93, v95);
                  }
                  while ( v96 != v95 );
                  do
                  {
                    v97 = *(_QWORD *)(v94 + 8352);
                    v98 = v97;
                    if ( v93 > v97 )
                      v98 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8352), v93, v97);
                  }
                  while ( v98 != v97 );
                  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                  v42 = (char *)v117;
                }
                v99 = *(_QWORD **)v42;
                if ( *(char **)(*(_QWORD *)v42 + 8LL) != v42 || (v100 = (PVOID *)*((_QWORD *)v42 + 1), *v100 != v42) )
LABEL_267:
                  __fastfail(3u);
                *v100 = v99;
                v99[1] = v100;
                if ( v42 == (char *)(a2 + 1624) || v42 == (char *)(a2 + 1688) )
                {
                  *(_QWORD *)v42 = 0;
                  FsRtlResetBaseMcb((PBASE_MCB)(v42 + 16));
                }
                else
                {
                  FsRtlUninitializeBaseMcb((PBASE_MCB)(v42 + 16));
                  ExFreeToLookasideListEx(&NtfsDeallocatedClustersLookasideList, v42);
                }
              }
              v9 = v76;
              v117 = v76;
              v131 = v76;
              goto LABEL_13;
            }
            if ( (unsigned int)v73 + NextForwardRunClear <= v72 )
            {
              v75 = NextForwardRunClear;
            }
            else
            {
              if ( (unsigned int)v73 >= v72 )
                goto LABEL_185;
              v75 = v72 - v73;
            }
            if ( !v74 )
              break;
            if ( !v67 )
            {
              v67 = NtfsAddCachedRun(v5, a2, Lbn + (unsigned int)v73, v75, 2, 1) == 0;
              v119 = v67;
              goto LABEL_177;
            }
LABEL_178:
            v73 = NextForwardRunClear + (unsigned int)v73;
            StartingIndex = v73;
            if ( (unsigned int)v73 >= v72 )
            {
              NextForwardRunClear = 0;
            }
            else
            {
              NextForwardRunClear = RtlFindNextForwardRunClear(&BitMapHeader, v73, &StartingIndex);
              v72 = v116;
              v73 = StartingIndex;
              v74 = v110;
            }
            if ( v74 )
            {
              if ( v67 )
                goto LABEL_185;
            }
            else if ( v68 )
            {
              goto LABEL_185;
            }
          }
          NtfsSendUnusedClustersHint(v5, Lbn + v73, v75, &v126, v114);
          v68 = v114[0];
LABEL_177:
          v74 = v110;
          LODWORD(v73) = StartingIndex;
          v72 = v116;
          goto LABEL_178;
        }
        if ( Status != -1073741808
          && Status != -1073741822
          && (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
        {
          McTemplateU0pd_EtwWriteTransfer(v64, (const EVENT_DESCRIPTOR *)logsup_c7850, a2, Status);
        }
        *(_DWORD *)(a2 + 5524) &= ~1u;
        v17 = v116;
        goto LABEL_197;
      }
      if ( P != &v125 )
      {
        ExFreePoolWithTag(P, 0);
        P = 0;
        v17 = v116;
      }
    }
    v57 = OutputBufferLength;
    v128 = OutputBufferLength;
    if ( OutputBufferLength > 4 )
    {
      PoolWithTag = (int *)ExAllocatePoolWithTag((POOL_TYPE)512, OutputBufferLength, 0x4C46744Eu);
      P = PoolWithTag;
      v17 = v116;
      v57 = v128;
    }
    else
    {
      PoolWithTag = &v125;
      P = &v125;
    }
    goto LABEL_140;
  }
  if ( (!v5 || (*(_DWORD *)(v5 + 16) & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
  {
    v13 = a2;
    v14 = logsup_c7313;
LABEL_30:
    McTemplateU0p_EtwWriteTransfer((__int64)v10, (const EVENT_DESCRIPTOR *)v14, v13);
  }
LABEL_31:
  if ( !v111 )
  {
    v15 = *(_QWORD *)(a2 + 1608);
    if ( v15 == a2 + 1608 )
    {
      v15 = 0;
    }
    else if ( v15 )
    {
      if ( FsRtlNumberOfRunsInBaseMcb((PBASE_MCB)(v15 + 16)) <= 0x200 )
      {
        v101 = *(_DWORD *)(v15 + 56);
        if ( (v101 & 1) == 0 && (v101 & 0x30) == 0 && !*(_QWORD *)(v15 + 48) )
          goto LABEL_288;
      }
    }
    v135 = 0;
    v102 = (char *)(a2 + 1624);
    if ( *(_QWORD *)(a2 + 1624) )
    {
      v102 = 0;
      if ( !*(_QWORD *)(a2 + 1688) )
        v102 = (char *)(a2 + 1688);
    }
    v135 = v102;
    if ( v102 )
    {
      *((_QWORD *)v102 + 5) = 0;
      *((_DWORD *)v102 + 14) = 0;
      *((_QWORD *)v102 + 6) = 0;
    }
    else
    {
      v103 = (char *)ExAllocateFromLookasideListEx(&NtfsDeallocatedClustersLookasideList);
      v102 = v103;
      v135 = v103;
      if ( v103 )
      {
        *(_OWORD *)v103 = 0;
        *((_OWORD *)v103 + 1) = 0;
        *((_OWORD *)v103 + 2) = 0;
        *((_OWORD *)v103 + 3) = 0;
        FsRtlInitializeBaseMcbEx((PBASE_MCB)(v103 + 16), PoolType, 1u);
      }
    }
    if ( v102 )
    {
      if ( v15 )
      {
        *(_QWORD *)(v15 + 40) = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
        *(_QWORD *)(v5 + 16) |= 0x4000000uLL;
        if ( (*(_QWORD *)(v5 + 16) & 0x100000LL) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
        {
          McTemplateU0pp_EtwWriteTransfer(v104, (const EVENT_DESCRIPTOR *)strucsup_c17526, v15, *(_QWORD *)(v15 + 40));
        }
      }
      v105 = (_QWORD *)(a2 + 1608);
      v106 = *(_QWORD *)(a2 + 1608);
      if ( *(_QWORD *)(v106 + 8) != a2 + 1608 )
        __fastfail(3u);
      *(_QWORD *)v102 = v106;
      *((_QWORD *)v102 + 1) = v105;
      *(_QWORD *)(v106 + 8) = v102;
      *v105 = v102;
    }
  }
LABEL_288:
  if ( (*(_DWORD *)(v5 + 16) & 0x200LL) != 0 && (*(_DWORD *)(a2 + 5524) & 6) == 2 )
  {
    NtfsPostSpecial(v5, *(_QWORD *)(v5 + 104), NtfsBackgroundBitmapScanWorker, 0, 32);
    *(_DWORD *)(a2 + 5524) |= 4u;
  }
  NtfsReleaseFcbEx(v5, *(_QWORD *)(*(_QWORD *)(a2 + 72) + 184LL), 0);
  if ( P )
  {
    a1 = &v125;
    if ( P != &v125 )
      ExFreePoolWithTag(P, 0);
  }
  if ( (*(_DWORD *)(v5 + 16) & 0x100000LL) == 0
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
  {
    v8 = logsup_c8159;
    goto LABEL_301;
  }
}

```

## disassembly

```asm
0x14020f350  mov     [rsp+arg_18], r9b
0x14020f355  push    rbx
0x14020f356  push    rsi
0x14020f357  push    rdi
0x14020f358  push    r12
0x14020f35a  push    r13
0x14020f35c  push    r14
0x14020f35e  push    r15
0x14020f360  sub     rsp, 220h
0x14020f367  mov     rax, cs:__security_cookie
0x14020f36e  xor     rax, rsp
0x14020f371  mov     [rsp+258h+var_48], rax
0x14020f379  mov     r13, rdx
0x14020f37c  mov     r15, rcx
0x14020f37f  mov     [rsp+258h+var_120], r8
0x14020f387  mov     [rsp+258h+var_188], rcx
0x14020f38f  mov     [rsp+258h+var_190], rdx
0x14020f397  xor     r14d, r14d
0x14020f39a  mov     [rsp+258h+var_1A8], r14d
0x14020f3a2  xorps   xmm0, xmm0
0x14020f3a5  movups  xmmword ptr [rsp+258h+Entry], xmm0
0x14020f3ad  xorps   xmm1, xmm1
0x14020f3b0  movups  xmmword ptr [rsp+258h+var_1D0], xmm1
0x14020f3b8  test    rcx, rcx
0x14020f3bb  jz      short loc_14020F3C7
0x14020f3bd  mov     eax, [rcx+10h]
0x14020f3c0  bt      rax, 14h
0x14020f3c5  jb      short loc_14020F3E7
0x14020f3c7  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f3ce  jz      short loc_14020F3E7
0x14020f3d0  movzx   eax, [rsp+258h+arg_18]
0x14020f3d8  mov     dword ptr [rsp+258h+SectorCount], eax
0x14020f3dc  mov     r9, [r8]
0x14020f3df  mov     r8, r13
0x14020f3e2  call    McTemplateU0piq_EtwWriteTransfer
0x14020f3e7  lea     rdi, [r13+648h]
0x14020f3ee  cmp     [rdi], rdi
0x14020f3f1  jz      loc_140210ABE
0x14020f3f7  mov     rdx, [r13+48h]
0x14020f3fb  test    rdx, rdx
0x14020f3fe  jz      loc_140210ABE
0x14020f404  mov     [rsp+258h+var_108], r13
0x14020f40c  mov     [rsp+258h+var_B8], rdi
0x14020f414  xor     r8d, r8d
0x14020f417  mov     rcx, r15
0x14020f41a  call    NtfsAcquireExclusiveScbEx
0x14020f41f  cmp     [rdi], rdi
0x14020f422  jnz     short loc_14020F467
0x14020f424  mov     rdx, [r13+48h]
0x14020f428  xor     r8d, r8d
0x14020f42b  mov     rdx, [rdx+0B8h]
0x14020f432  mov     rcx, r15
0x14020f435  call    NtfsReleaseFcbEx
0x14020f43a  test    r15, r15
0x14020f43d  jz      short loc_14020F44E
0x14020f43f  mov     eax, [r15+10h]
0x14020f443  bt      rax, 14h
0x14020f448  jb      loc_140210AE6
0x14020f44e  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f455  jz      loc_140210AE6
0x14020f45b  lea     rdx, logsup_c7231
0x14020f462  jmp     loc_140210ADE
0x14020f467  mov     [rsp+258h+var_180], r14d
0x14020f46f  mov     [rsp+258h+P], r14
0x14020f477  mov     [rsp+258h+var_207], r14b
0x14020f47c  mov     [rsp+258h+var_206], r14b
0x14020f481  mov     [rsp+258h+var_205], r14b
0x14020f486  mov     [rsp+258h+var_A0], rdi
0x14020f48e  mov     [rsp+258h+var_A8], rdi
0x14020f496  movzx   edx, byte ptr [r13+1591h]
0x14020f49e  mov     [rsp+258h+var_208], dl
0x14020f4a2  mov     [rsp+258h+var_203], dl
0x14020f4a6  mov     rdi, [r13+650h]
0x14020f4ad  mov     [rsp+258h+var_1F0], rdi
0x14020f4b2  mov     [rsp+258h+var_170], rdi
0x14020f4ba  mov     esi, 1
0x14020f4bf  nop
0x14020f4c0  mov     rcx, [rsp+258h+var_B8]
0x14020f4c8  cmp     [rcx], rcx
0x14020f4cb  jz      loc_14020F590
0x14020f4d1  cmp     [rsp+258h+var_207], 0
0x14020f4d6  jnz     loc_14021099B
0x14020f4dc  lea     rbx, [rdi+38h]
0x14020f4e0  mov     [rsp+258h+var_110], rbx
0x14020f4e8  mov     r8d, [rbx]
0x14020f4eb  mov     edx, r8d
0x14020f4ee  and     edx, 1
0x14020f4f1  jnz     short loc_14020F519
0x14020f4f3  test    r8b, 30h
0x14020f4f7  jnz     short loc_14020F519
0x14020f4f9  mov     rcx, [rdi+28h]
0x14020f4fd  test    rcx, rcx
0x14020f500  jz      short loc_14020F50F
0x14020f502  mov     rax, [rsp+258h+var_120]
0x14020f50a  cmp     [rax], rcx
0x14020f50d  jg      short loc_14020F519
0x14020f50f  cmp     [rsp+258h+arg_18], 0
0x14020f517  jz      short loc_14020F590
0x14020f519  test    edx, edx
0x14020f51b  jz      loc_14020F5BB
0x14020f521  test    r15, r15
0x14020f524  jz      short loc_14020F531
0x14020f526  mov     eax, [r15+10h]
0x14020f52a  bt      rax, 14h
0x14020f52f  jb      short loc_14020F54D
0x14020f531  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14020f538  jz      short loc_14020F54D
0x14020f53a  mov     r9, [rdi+30h]
0x14020f53e  mov     r8, r13
0x14020f541  lea     rdx, logsup_c7283
0x14020f548  call    McTemplateU0pp_EtwWriteTransfer
0x14020f54d  mov     rdi, [rdi+8]
0x14020f551  mov     [rsp+258h+var_1F0], rdi
0x14020f556  mov     [rsp+258h+var_170], rdi
0x14020f55e  cmp     rdi, [rsp+258h+var_A8]
0x14020f566  jnz     short loc_14020F5B6
0x14020f568  test    r15, r15
0x14020f56b  jz      short loc_14020F578
0x14020f56d  mov     eax, [r15+10h]
0x14020f571  bt      rax, 14h
0x14020f576  jb      short loc_14020F590
0x14020f578  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f57f  jz      short loc_14020F590
0x14020f581  mov     r8, r13
0x14020f584  lea     rdx, logsup_c7298
0x14020f58b  call    McTemplateU0p_EtwWriteTransfer
0x14020f590  cmp     [rsp+258h+var_207], 0
0x14020f595  jnz     loc_14021099B
0x14020f59b  lea     rax, [r13+648h]
0x14020f5a2  mov     rdi, [rax]
0x14020f5a5  cmp     rdi, rax
0x14020f5a8  jnz     loc_14021085A
0x14020f5ae  mov     rdi, r14
0x14020f5b1  jmp     loc_14021088C
0x14020f5b6  jmp     loc_14020F4C0
0x14020f5bb  mov     [rsp+258h+var_90], rdi
0x14020f5c3  mov     [rsp+258h+var_98], rbx
0x14020f5cb  cmp     rdi, [rsp+258h+var_A0]
0x14020f5d3  jnz     short loc_14020F5FA
0x14020f5d5  test    r15, r15
0x14020f5d8  jz      short loc_14020F5E5
0x14020f5da  mov     eax, [r15+10h]
0x14020f5de  bt      rax, 14h
0x14020f5e3  jb      short loc_14020F590
0x14020f5e5  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f5ec  jz      short loc_14020F590
0x14020f5ee  mov     r8, r13
0x14020f5f1  lea     rdx, logsup_c7313
0x14020f5f8  jmp     short loc_14020F58B
0x14020f5fa  mov     r12d, r14d
0x14020f5fd  mov     [rsp+258h+var_200], r14d
0x14020f602  mov     [rsp+258h+var_204], 0
0x14020f607  mov     [rsp+258h+var_1A0], r14
0x14020f60f  mov     [rsp+258h+var_17C], r14d
0x14020f617  mov     [rsp+258h+Vbn], r14
0x14020f61f  mov     [rsp+258h+Lbn], r14
0x14020f627  mov     [rsp+258h+var_1F8], r14
0x14020f62c  mov     rcx, [rdi+30h]
0x14020f630  test    rcx, rcx
0x14020f633  jle     loc_1402103C2
0x14020f639  test    r15, r15
0x14020f63c  jz      short loc_14020F649
0x14020f63e  mov     eax, [r15+10h]
0x14020f642  bt      rax, 14h
0x14020f647  jb      short loc_14020F677
0x14020f649  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14020f650  jz      short loc_14020F677
0x14020f652  mov     dword ptr [rsp+258h+InternalDeviceIoControl], r8d
0x14020f657  mov     rax, [rdi+28h]
0x14020f65b  mov     qword ptr [rsp+258h+OutputBufferLength], rax
0x14020f660  mov     [rsp+258h+SectorCount], rcx
0x14020f665  mov     r9, rdi
0x14020f668  mov     r8, r13
0x14020f66b  lea     rdx, logsup_c7352
0x14020f672  call    McTemplateU0ppiid_EtwWriteTransfer
0x14020f677  mov     r12d, r14d
0x14020f67a  mov     [rsp+258h+var_17C], r12d
0x14020f682  lea     rcx, [rdi+10h]; Mcb
0x14020f686  lea     rax, [rsp+258h+var_1F8]
0x14020f68b  mov     [rsp+258h+SectorCount], rax; SectorCount
0x14020f690  lea     r9, [rsp+258h+Lbn]; Lbn
0x14020f698  lea     r8, [rsp+258h+Vbn]; Vbn
0x14020f6a0  mov     edx, r12d; RunIndex
0x14020f6a3  call    cs:__imp_FsRtlGetNextBaseMcbEntry
0x14020f6aa  nop     dword ptr [rax+rax+00h]
0x14020f6af  test    al, al
0x14020f6b1  jz      loc_140210396
0x14020f6b7  mov     rdi, [rsp+258h+Lbn]
0x14020f6bf  cmp     [rsp+258h+Vbn], rdi
0x14020f6c7  jnz     loc_140210389
0x14020f6cd  mov     rcx, [rsp+258h+var_1F8]
0x14020f6d2  mov     rsi, rcx
0x14020f6d5  test    r15, r15
0x14020f6d8  jz      short loc_14020F6E5
0x14020f6da  mov     eax, [r15+10h]
0x14020f6de  bt      rax, 14h
0x14020f6e3  jb      short loc_14020F71E
0x14020f6e5  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 2
0x14020f6ec  jz      short loc_14020F71E
0x14020f6ee  mov     qword ptr [rsp+258h+InternalDeviceIoControl], rcx
0x14020f6f3  mov     rax, [rsp+258h+Lbn]
0x14020f6fb  mov     qword ptr [rsp+258h+OutputBufferLength], rax
0x14020f700  mov     dword ptr [rsp+258h+SectorCount], r12d
0x14020f705  mov     r9, [rsp+258h+var_1F0]
0x14020f70a  mov     r8, r13
0x14020f70d  lea     rdx, logsup_c7375
0x14020f714  call    McTemplateU0ppdii_EtwWriteTransfer
0x14020f719  mov     rcx, [rsp+258h+var_1F8]
0x14020f71e  test    dword ptr [r13+18h], 40000h
0x14020f726  jz      loc_14020FD38
0x14020f72c  mov     eax, [rbx]
0x14020f72e  test    al, 10h
0x14020f730  jnz     loc_14020FD38
0x14020f736  test    r15, r15
0x14020f739  jz      short loc_14020F746
0x14020f73b  mov     eax, [r15+10h]
0x14020f73f  bt      rax, 14h
0x14020f744  jb      short loc_14020F760
0x14020f746  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 2
0x14020f74d  jz      short loc_14020F760
0x14020f74f  lea     rdx, logsup_c7398
0x14020f756  call    McTemplateU0_EtwWriteTransfer
0x14020f75b  mov     rcx, [rsp+258h+var_1F8]
0x14020f760  lea     rax, [rsp+258h+Entry]
0x14020f768  mov     [rsp+258h+Entry+8], rax
0x14020f770  lea     rax, [rsp+258h+Entry]
0x14020f778  mov     [rsp+258h+Entry], rax
0x14020f780  mov     [rsp+258h+var_206], 1
0x14020f785  lea     rax, [rsp+258h+var_1D0]
0x14020f78d  mov     [rsp+258h+var_1D0+8], rax
0x14020f795  lea     rax, [rsp+258h+var_1D0]
0x14020f79d  mov     [rsp+258h+var_1D0], rax
0x14020f7a5  mov     [rsp+258h+var_205], 1
0x14020f7aa  mov     qword ptr [rsp+258h+InternalDeviceIoControl], r14
0x14020f7af  lea     rax, [rsp+258h+var_1D0]
0x14020f7b7  mov     qword ptr [rsp+258h+OutputBufferLength], rax
0x14020f7bc  lea     rax, [rsp+258h+Entry]
0x14020f7c4  mov     [rsp+258h+SectorCount], rax
0x14020f7c9  mov     r9d, [r13+164h]
0x14020f7d0  mov     r8, rcx
0x14020f7d3  mov     rdx, [rsp+258h+Lbn]
0x14020f7db  mov     rcx, [r13+0E0h]
0x14020f7e2  call    FsLibGroupSubExtentsByDanglingMdl
0x14020f7e7  mov     [rsp+258h+var_1C0], eax
0x14020f7ee  test    eax, eax
0x14020f7f0  jns     loc_14020F8CF
0x14020f7f6  test    r15, r15
0x14020f7f9  jz      short loc_14020F806
0x14020f7fb  mov     ecx, [r15+10h]
0x14020f7ff  bt      rcx, 14h
0x14020f804  jb      short loc_14020F81E
0x14020f806  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 4
0x14020f80d  jz      short loc_14020F81E
0x14020f80f  mov     r8d, eax
0x14020f812  lea     rdx, logsup_c7423
0x14020f819  call    McTemplateU0q_EtwWriteTransfer
0x14020f81e  lea     rcx, [rsp+258h+var_1D0]
0x14020f826  call    FsLibUninitializeExtentList
0x14020f82b  lea     rax, [rsp+258h+var_1D0]
0x14020f833  mov     [rsp+258h+var_1D0+8], rax
0x14020f83b  lea     rax, [rsp+258h+var_1D0]
0x14020f843  mov     [rsp+258h+var_1D0], rax
0x14020f84b  lea     rcx, [rsp+258h+Entry]
0x14020f853  call    FsLibUninitializeExtentList
0x14020f858  lea     rax, [rsp+258h+Entry]
0x14020f860  mov     [rsp+258h+Entry+8], rax
0x14020f868  lea     rax, [rsp+258h+Entry]
0x14020f870  mov     [rsp+258h+Entry], rax
0x14020f878  mov     r8, [rsp+258h+var_1F8]
0x14020f87d  mov     rdx, [rsp+258h+Lbn]
0x14020f885  lea     rcx, [rsp+258h+Entry]
0x14020f88d  call    FsLibAppendExtent
0x14020f892  mov     [rsp+258h+var_1C0], eax
0x14020f899  test    eax, eax
0x14020f89b  jns     short loc_14020F8CF
0x14020f89d  test    r15, r15
0x14020f8a0  jz      short loc_14020F8AD
0x14020f8a2  mov     ecx, [r15+10h]
0x14020f8a6  bt      rcx, 14h
0x14020f8ab  jb      short loc_14020F8C5
0x14020f8ad  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 4
0x14020f8b4  jz      short loc_14020F8C5
0x14020f8b6  mov     r8d, eax
0x14020f8b9  lea     rdx, logsup_c7441
0x14020f8c0  call    McTemplateU0q_EtwWriteTransfer
0x14020f8c5  mov     [rsp+258h+var_207], 1
0x14020f8ca  jmp     loc_1402103C9
0x14020f8cf  mov     [rsp+258h+var_1F8], r14
0x14020f8d4  lea     rax, [rsp+258h+var_1D0]
0x14020f8dc  mov     rbx, [rsp+258h+var_1D0]
0x14020f8e4  cmp     rbx, rax
0x14020f8e7  jz      loc_14020FBC0
0x14020f8ed  lea     r11, [rsp+258h+var_1D0]
0x14020f8f5  mov     [rsp+258h+var_E8], r11
0x14020f8fd  mov     [rsp+258h+var_E0], r14
0x14020f905  mov     rcx, rbx
0x14020f908  mov     [rsp+258h+var_E0], rbx
0x14020f910  mov     r8, r14
0x14020f913  mov     [rsp+258h+var_D8], r14
0x14020f91b  mov     rax, r14
  ... truncated ...
```
