# DxgkSubmitCommandInternal(_D3DKMT_SUBMITCOMMAND const *,DXGPROCESS *)

- ea: `0x14032cf7c`
- end: `0x14032e5cc`
- name: `?DxgkSubmitCommandInternal@@YAJPEBU_D3DKMT_SUBMITCOMMAND@@PEAVDXGPROCESS@@@Z`
- size: `5712`
- prototype: `__int64 __fastcall(const struct _D3DKMT_SUBMITCOMMAND *, struct DXGPROCESS *)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1401c1e40`
- `0x14032c520`

## callees

- `0x14000d990`
- `0x140012cd4`
- `0x140013a20`
- `0x140015a70`
- `0x140015b30`
- `0x1400164f0`
- `0x1400169f0`
- `0x140016d34`
- `0x140018054`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bbd0`
- `0x14001c450`
- `0x14001c790`
- `0x14001cd10`
- `0x14001ce20`
- `0x14001d214`
- `0x14001f2f0`
- `0x140020320`
- `0x14002ef40`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x140195ea8`
- `0x1401e7780`
- `0x140252c68`
- `0x14032c648`
- `0x14032cf7c`
- `0x14032e8a0`
- `0x14032e980`
- `0x14037ecf0`
- `0x1403924e4`
- `0x140394f80`
- `0x140400790`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14032d424`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d4c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d6e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d788`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d9d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032daca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032dbc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032dc95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032e073`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032e1ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032e3e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d424`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d4c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d6e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d788`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032d9d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032daca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032dbc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032dc95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032e073`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032e1ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032e3e3`
- `ntoskrnl!ExAllocatePool2` at `0x14032d4ff`
- `ntoskrnl!ExAllocatePool2` at `0x14032d4ff`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14032d010`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14032d010`
- `watchdog!WdLogSingleEntry4` at `0x14032d8f4`
- `watchdog!WdLogSingleEntry4` at `0x14032de31`
- `watchdog!WdLogSingleEntry4` at `0x14032e537`
- `watchdog!WdLogSingleEntry4` at `0x14032d8f4`
- `watchdog!WdLogSingleEntry4` at `0x14032de31`
- `watchdog!WdLogSingleEntry4` at `0x14032e537`
- `watchdog!WdLogSingleEntry2` at `0x14032d54a`
- `watchdog!WdLogSingleEntry2` at `0x14032e31c`
- `watchdog!WdLogSingleEntry2` at `0x14032d54a`
- `watchdog!WdLogSingleEntry2` at `0x14032e31c`
- `watchdog!WdLogSingleEntry3` at `0x14032da29`
- `watchdog!WdLogSingleEntry3` at `0x14032dd7b`
- `watchdog!WdLogSingleEntry3` at `0x14032e0e3`
- `watchdog!WdLogSingleEntry3` at `0x14032da29`
- `watchdog!WdLogSingleEntry3` at `0x14032dd7b`
- `watchdog!WdLogSingleEntry3` at `0x14032e0e3`
- `watchdog!WdLogSingleEntry0` at `0x14032d72d`
- `watchdog!WdLogSingleEntry0` at `0x14032d7fa`
- `watchdog!WdLogSingleEntry0` at `0x14032db09`
- `watchdog!WdLogSingleEntry0` at `0x14032dbde`
- `watchdog!WdLogSingleEntry0` at `0x14032dcf6`
- `watchdog!WdLogSingleEntry0` at `0x14032dd13`
- `watchdog!WdLogSingleEntry0` at `0x14032ddfe`
- `watchdog!WdLogSingleEntry0` at `0x14032de8b`
- `watchdog!WdLogSingleEntry0` at `0x14032df17`
- `watchdog!WdLogSingleEntry0` at `0x14032d72d`
- `watchdog!WdLogSingleEntry0` at `0x14032d7fa`
- `watchdog!WdLogSingleEntry0` at `0x14032db09`
- `watchdog!WdLogSingleEntry0` at `0x14032dbde`
- `watchdog!WdLogSingleEntry0` at `0x14032dcf6`
- `watchdog!WdLogSingleEntry0` at `0x14032dd13`
- `watchdog!WdLogSingleEntry0` at `0x14032ddfe`
- `watchdog!WdLogSingleEntry0` at `0x14032de8b`
- `watchdog!WdLogSingleEntry0` at `0x14032df17`
- `watchdog!WdLogSingleEntry1` at `0x14032d3b3`
- `watchdog!WdLogSingleEntry1` at `0x14032d65f`
- `watchdog!WdLogSingleEntry1` at `0x14032ddc3`
- `watchdog!WdLogSingleEntry1` at `0x14032def0`
- `watchdog!WdLogSingleEntry1` at `0x14032dfb6`
- `watchdog!WdLogSingleEntry1` at `0x14032d3b3`
- `watchdog!WdLogSingleEntry1` at `0x14032d65f`
- `watchdog!WdLogSingleEntry1` at `0x14032ddc3`
- `watchdog!WdLogSingleEntry1` at `0x14032def0`
- `watchdog!WdLogSingleEntry1` at `0x14032dfb6`

## string_xrefs

- `0x14032dded`: `DXGCONTEXT 0x%p is hardware scheduled and should not be passed to SubmitCommandCb.`
- `0x14032df06`: `DXGCONTEXT 0x%p is hardware scheduled and should not be passed to SubmitCommandCb.`
- `0x14032dfee`: `Invalid history buffer handle provided to SubmitCommand. D3DKMT_HANDLE=0x%8x`
- `0x14032db3b`: `Invalid history buffer passed to SubmitCommand.`
- `0x14032dc0e`: `Failed to created paged pool array for history buffer array`
- `0x14032dd07`: `NoKmdAccess can be used only with testsigning`

## pseudocode

```c
__int64 __fastcall DxgkSubmitCommandInternal(struct _D3DKMT_SUBMITCOMMAND *a1, struct DXGPROCESS *a2, __int64 a3)
{
  struct _D3DKMT_SUBMITCOMMAND *v5; // rdi
  D3DKMT_SUBMITCOMMANDFLAGS Flags; // edx
  struct DXGCONTEXT *v7; // rsi
  int v8; // eax
  __int64 BroadcastContextCount; // r14
  __int64 v10; // rcx
  PVOID Pool2; // rcx
  int v12; // r9d
  signed __int64 v13; // rax
  signed __int64 v14; // rtt
  unsigned int v15; // r9d
  __int64 v16; // r13
  int v17; // r12d
  struct VIDMM_MULTI_ALLOC **v18; // r13
  int v19; // r14d
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned int v23; // edi
  __int64 v24; // rcx
  __int64 v25; // r8
  int v26; // r8d
  unsigned __int64 PresentHistoryToken; // rdx
  unsigned int v28; // eax
  unsigned int *v29; // rdi
  __int64 v30; // rcx
  __int64 v31; // r8
  bool v32; // zf
  __int64 v33; // rcx
  __int64 v34; // r8
  bool v35; // zf
  const wchar_t *v36; // r9
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v40; // rcx
  __int64 v41; // r13
  struct DXGCONTEXT *v42; // r8
  int v43; // ecx
  int v44; // ecx
  signed __int64 v45; // rax
  signed __int64 v46; // rtt
  __int64 v47; // rsi
  __int64 v48; // rax
  const wchar_t *v49; // r9
  const wchar_t *v50; // r9
  struct VIDMM_MULTI_ALLOC **NumPrimaries; // rax
  __int64 Elements; // r12
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // rcx
  __int64 v57; // r8
  D3DKMT_HANDLE *HistoryBufferArray; // rax
  unsigned int ULongFromUser; // eax
  __int64 v60; // r8
  __int64 AllocationSafe; // rax
  __int64 v62; // rcx
  __int64 v63; // rcx
  struct VIDMM_MULTI_ALLOC **v64; // [rsp+28h] [rbp-4D0h]
  __int64 v65; // [rsp+30h] [rbp-4C8h]
  __int64 v66; // [rsp+38h] [rbp-4C0h]
  unsigned int v67; // [rsp+50h] [rbp-4A8h] BYREF
  __int64 v68; // [rsp+58h] [rbp-4A0h]
  char v69; // [rsp+60h] [rbp-498h]
  char CurrentThreadPreviousMode; // [rsp+68h] [rbp-490h]
  unsigned __int8 v71; // [rsp+69h] [rbp-48Fh]
  PVOID P; // [rsp+70h] [rbp-488h]
  _BYTE v73[32]; // [rsp+78h] [rbp-480h] BYREF
  unsigned int v74; // [rsp+98h] [rbp-460h]
  _BYTE v75[16]; // [rsp+A0h] [rbp-458h] BYREF
  struct DXGCONTEXT *v76; // [rsp+B0h] [rbp-448h] BYREF
  unsigned int v77; // [rsp+B8h] [rbp-440h]
  PVOID v78; // [rsp+C0h] [rbp-438h] BYREF
  int v79; // [rsp+C8h] [rbp-430h]
  _BYTE v80[16]; // [rsp+D0h] [rbp-428h] BYREF
  _BYTE v81[8]; // [rsp+E0h] [rbp-418h] BYREF
  __int64 v82; // [rsp+E8h] [rbp-410h]
  char v83; // [rsp+F0h] [rbp-408h]
  int v84; // [rsp+F8h] [rbp-400h]
  struct DXGPROCESS *v85; // [rsp+100h] [rbp-3F8h]
  __int64 v86; // [rsp+108h] [rbp-3F0h]
  struct DXGPROCESS *v87; // [rsp+110h] [rbp-3E8h]
  _BYTE v88[8]; // [rsp+118h] [rbp-3E0h] BYREF
  __int64 v89; // [rsp+120h] [rbp-3D8h]
  __int64 v90; // [rsp+128h] [rbp-3D0h]
  _QWORD v91[6]; // [rsp+130h] [rbp-3C8h] BYREF
  char v92; // [rsp+160h] [rbp-398h]
  _BYTE v93[24]; // [rsp+168h] [rbp-390h] BYREF
  _BYTE v94[160]; // [rsp+180h] [rbp-378h] BYREF
  void *v95; // [rsp+220h] [rbp-2D8h] BYREF
  char v96; // [rsp+228h] [rbp-2D0h] BYREF
  int v97; // [rsp+2A8h] [rbp-250h]
  _QWORD v98[17]; // [rsp+2B0h] [rbp-248h] BYREF
  int v99; // [rsp+338h] [rbp-1C0h]
  _BYTE v100[384]; // [rsp+340h] [rbp-1B8h] BYREF

  v85 = a2;
  v87 = a2;
  v67 = -1;
  v68 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v69 = 1;
    v67 = 2102;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 2102);
  }
  else
  {
    v69 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v67, 2102);
  CurrentThreadPreviousMode = PsGetCurrentThreadPreviousMode();
  v71 = CurrentThreadPreviousMode == 1;
  memset(v100, 0, sizeof(v100));
  v5 = (struct _D3DKMT_SUBMITCOMMAND *)v100;
  if ( CurrentThreadPreviousMode == 1 )
    RtlCopyFromUser(v100, a1, 0x180u);
  else
    v5 = a1;
  Flags = v5->Flags;
  if ( (*(_BYTE *)&Flags & 4) != 0 && !g_OSTestSigningEnabled )
  {
    WdLogSingleEntry0(2);
    v48 = 1686;
    v49 = L"NoKmdAccess can be used only with testsigning";
LABEL_117:
    WdLogGlobalForLineNumber = v48;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v49, v48, 0, 0, 0, 0);
LABEL_57:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
    v32 = v69 == 0;
LABEL_58:
    if ( !v32 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v30, EventProfilerExit, v31, v67);
    return 3221225485LL;
  }
  if ( (*((_DWORD *)a2 + 102) & 0x100) != 0 && (*(_BYTE *)&Flags & 2) != 0 )
  {
    WdLogSingleEntry0(2);
    v48 = 1694;
    v49 = L"PresentRedirected is invalid from virtual machine";
    goto LABEL_117;
  }
  v76 = 0;
  DXGCONTEXTBYHANDLE::DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75, v5->BroadcastContext[0], a2, &v76, 0, 1);
  v7 = v76;
  if ( !v76 )
  {
    WdLogSingleEntry3(2, a2, v5->BroadcastContext[0], -1073741811);
    WdLogGlobalForLineNumber = 1704;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"0x%I64x failed with invalid hContext 0x%I64x returning 0x%I64x",
      (__int64)a2,
      v5->BroadcastContext[0],
      -1073741811,
      0,
      0);
LABEL_56:
    DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
    goto LABEL_57;
  }
  v8 = *((_DWORD *)v76 + 98);
  if ( (v8 & 0x10) != 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 1711;
    v66 = 0;
    v65 = 0;
    v64 = 0;
    v50 = L"DXGCONTEXT 0x%p is hardware scheduled and should not be passed to SubmitCommandCb.";
LABEL_166:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v50, (__int64)v7, (__int64)v64, v65, v66, 0);
    goto LABEL_56;
  }
  if ( (v8 & 8) != 0 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1718;
    goto LABEL_56;
  }
  BroadcastContextCount = v5->BroadcastContextCount;
  if ( (unsigned int)(BroadcastContextCount - 1) > 0x3F )
  {
    WdLogSingleEntry4(2, v76, v5->BroadcastContextCount, 64, -1073741811);
    WdLogGlobalForLineNumber = 1731;
    NumPrimaries = (struct VIDMM_MULTI_ALLOC **)v5->BroadcastContextCount;
    v66 = -1073741811;
    v65 = 64;
    v50 = L"0x%I64x fails as specified BroadcastContextCount 0x%I64x exceeds limit 0x%I64x or is zero. returning 0x%I64x";
    goto LABEL_165;
  }
  if ( v5->NumPrimaries > 0x10 )
  {
    WdLogSingleEntry4(2, v76, v5->NumPrimaries, 16, -1073741811);
    WdLogGlobalForLineNumber = 1739;
    NumPrimaries = (struct VIDMM_MULTI_ALLOC **)v5->NumPrimaries;
    v66 = -1073741811;
    v65 = 16;
    v50 = L"0x%I64x fails as specified NumWrittenPrimaries 0x%I64x exceeds limit 0x%I64x returning 0x%I64x";
LABEL_165:
    v64 = NumPrimaries;
    goto LABEL_166;
  }
  v10 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v76 + 2) + 16LL) + 16LL);
  if ( *(_BYTE *)(v10 + 209) )
  {
    v23 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSubmitCommand((DXG_GUEST_VIRTUALGPU_VMBUS *)(v10 + 4792), a2, v5);
    DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
    if ( v69 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v24, EventProfilerExit, v25, v67);
    return v23;
  }
  Pool2 = 0;
  P = 0;
  v74 = 0;
  if ( (unsigned int)BroadcastContextCount > 4 )
  {
    v12 = 0;
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)BroadcastContextCount < 8 )
      goto LABEL_18;
    Pool2 = (PVOID)ExAllocatePool2(256, 8 * BroadcastContextCount, 1265072196);
    P = Pool2;
  }
  else
  {
    P = v73;
    memset(v73, 0, 8LL * (unsigned int)BroadcastContextCount);
    Pool2 = P;
  }
  v74 = BroadcastContextCount;
  v12 = BroadcastContextCount;
LABEL_18:
  if ( !Pool2 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 1755;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Out of memory - failed to allocate the broadcast context array",
      1755,
      0,
      0,
      0,
      0);
LABEL_75:
    if ( P != v73 && P )
      ExFreePoolWithTag(P, 0);
    P = 0;
    v74 = 0;
    DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
    v35 = v69 == 0;
    goto LABEL_63;
  }
  v78 = Pool2;
  v79 = v12;
  _m_prefetchw((char *)v7 + 32);
  v13 = *((_QWORD *)v7 + 4);
  do
  {
    if ( !v13 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1768;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DXGCONTEXT 0x%p failed to acquire reference.",
        (__int64)v7,
        0,
        0,
        0,
        0);
LABEL_38:
      ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
      if ( P != v73 && P )
        ExFreePoolWithTag(P, 0);
      P = 0;
      v74 = 0;
      goto LABEL_56;
    }
    v14 = v13;
    v13 = _InterlockedCompareExchange64((volatile signed __int64 *)v7 + 4, v13 + 1, v13);
  }
  while ( v14 != v13 );
  *(_QWORD *)P = v7;
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(
    (DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80,
    *((struct DXGDEVICE **)v7 + 2));
  DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v93, a2);
  v15 = 1;
  v77 = 1;
  while ( v15 < v5->BroadcastContextCount )
  {
    v42 = (struct DXGCONTEXT *)v15;
    v76 = (struct DXGCONTEXT *)v15;
    if ( ((v5->BroadcastContext[v15] >> 6) & 0xFFFFFF) < *((_DWORD *)a2 + 74)
      && (v43 = *(_DWORD *)(*((_QWORD *)a2 + 35) + 16LL * ((v5->BroadcastContext[v15] >> 6) & 0xFFFFFF) + 8),
          ((v5->BroadcastContext[v15] >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)a2 + 35)
                                                                  + 16LL * ((v5->BroadcastContext[v15] >> 6) & 0xFFFFFF)
                                                                  + 8)
                                                       & 0x60))
      && (v43 & 0x2000) == 0
      && (v43 & 0x1F) != 0 )
    {
      v40 = *((_QWORD *)a2 + 35);
      if ( (*(_BYTE *)(v40 + 16LL * ((v5->BroadcastContext[v15] >> 6) & 0xFFFFFF) + 8) & 0x1F) == 7 )
      {
        v41 = *(_QWORD *)(v40 + 16LL * ((v5->BroadcastContext[v15] >> 6) & 0xFFFFFF));
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        v41 = 0;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v42 = v76;
        v15 = v77;
      }
    }
    else
    {
      v41 = 0;
    }
    if ( !v41 || (v44 = *(_DWORD *)(v41 + 392), (v44 & 8) != 0) || *(_QWORD *)(v41 + 16) != *((_QWORD *)v7 + 2) )
    {
      WdLogSingleEntry4(2, v7, v41, v42, -1073741811);
      WdLogGlobalForLineNumber = 1806;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"0x%I64x failed with invalid broadcast context 0x%I64x at index %I64d returning 0x%I64x",
        (__int64)v7,
        v41,
        (__int64)v76,
        -1073741811,
        0);
      goto LABEL_69;
    }
    if ( (v44 & 0x10) != 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1814;
      v36 = L"DXGCONTEXT 0x%p is hardware scheduled and should not be passed to SubmitCommandCb.";
LABEL_68:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v36, v41, 0, 0, 0, 0);
LABEL_69:
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v93);
      DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
      ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
      if ( P != v73 && P )
        ExFreePoolWithTag(P, 0);
LABEL_72:
      P = 0;
      v74 = 0;
      DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
      v32 = v69 == 0;
      goto LABEL_58;
    }
    _m_prefetchw((const void *)(v41 + 32));
    v45 = *(_QWORD *)(v41 + 32);
    do
    {
      if ( !v45 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1821;
        v36 = L"DXGCONTEXT 0x%p failed to acquire reference.";
        goto LABEL_68;
      }
      v46 = v45;
      v45 = _InterlockedCompareExchange64((volatile signed __int64 *)(v41 + 32), v45 + 1, v45);
    }
    while ( v46 != v45 );
    *((_QWORD *)P + (_QWORD)v42) = v41;
    v77 = ++v15;
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v93);
  DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(
    v91,
    P,
    v74);
  if ( v92 )
  {
    if ( !v91[0] )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 1838;
      DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
      DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
      ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
      goto LABEL_75;
    }
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1843;
    DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
    goto LABEL_38;
  }
  v16 = *((_QWORD *)v7 + 2);
  v90 = v16;
  v82 = *(_QWORD *)(*(_QWORD *)(v16 + 16) + 16LL);
  v83 = 0;
  DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
  COREDEVICEACCESS::COREDEVICEACCESS(v94, v16, 0);
  v17 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v94, 0);
  v18 = 0;
  if ( v17 < 0 )
  {
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v94);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
    DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
    ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
    if ( P != v73 && P )
      ExFreePoolWithTag(P, 0);
LABEL_78:
    P = 0;
    v74 = 0;
    DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
    if ( v69 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v37, EventProfilerExit, v38, v67);
    return (unsigned int)v17;
  }
  if ( !*((_BYTE *)v7 + 430) )
  {
    v47 = (__int64)v85;
    WdLogSingleEntry3(2, v85, v5->BroadcastContext[0], -1073741811);
    WdLogGlobalForLineNumber = 1865;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"0x%I64x The context does not support virtual addressing. hContext 0x%I64x returning 0x%I64x",
      v47,
      v5->BroadcastContext[0],
      -1073741811,
      0,
      0);
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v94);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
    DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
    ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
    if ( P != v73 && P )
      ExFreePoolWithTag(P, 0);
    goto LABEL_72;
  }
  v98[0] = 0;
  v99 = 0;
  v95 = 0;
  v97 = 0;
  if ( !v5->NumHistoryBuffers )
  {
LABEL_28:
    if ( v5->CommandLength )
    {
      v19 = DXGCONTEXT::SubmitCommand(
              v7,
              v5,
              (struct COREDEVICEACCESS *)v94,
              (struct DXGADAPTERSTOPRESETLOCKSHARED *)v81,
              (struct DXGCONTEXT **)P,
              v18,
              v5->NumHistoryBuffers,
              v71);
      if ( v19 < 0 )
      {
LABEL_30:
        if ( v95 != &v96 )
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v95);
        PagedPoolArray<DXGALLOCATIONREFERENCE,16>::~PagedPoolArray<DXGALLOCATIONREFERENCE,16>(v98);
        COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v94);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
        DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
        DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
        ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
        if ( P != v73 && P )
          ExFreePoolWithTag(P, 0);
        P = 0;
        v74 = 0;
        DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
        if ( v69 )
        {
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v20, EventProfilerExit, v21, v67);
        }
        return (unsigned int)v19;
      }
    }
    else
    {
      v19 = 0;
    }
    v26 = (*(_DWORD *)&v5->Flags >> 1) & 1;
    if ( v26 )
    {
      PresentHistoryToken = v5->PresentHistoryToken;
    }
    else
    {
      v63 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 1960LL);
      PresentHistoryToken = 0;
      if ( v63 && *(_QWORD *)v63 && *(_DWORD *)(v63 + 12) != *((_DWORD *)v7 + 6) )
        PresentHistoryToken = *(_QWORD *)v63;
    }
    if ( PresentHistoryToken )
    {
      v28 = v5->BroadcastContextCount;
      if ( v28 <= 1 )
        v29 = 0;
      else
        v29 = &v5->BroadcastContext[1];
      v19 = DXGCONTEXT::HandleVistaBltStub(
              v7,
              PresentHistoryToken,
              v26,
              (struct COREDEVICEACCESS *)v94,
              (struct DXGADAPTERSTOPRESETLOCKSHARED *)v81,
              v28 - 1,
              v29,
              (struct DXGCONTEXT **)P);
    }
    goto LABEL_30;
  }
  Elements = PagedPoolArray<DXGALLOCATIONREFERENCE,16>::AllocateElements(v98);
  v86 = Elements;
  v53 = PagedPoolArray<VIDMM_MULTI_ALLOC *,16>::AllocateElements(&v95, v5->NumHistoryBuffers);
  v18 = (struct VIDMM_MULTI_ALLOC **)v53;
  if ( Elements )
  {
    Elements = 0;
    if ( v53 )
    {
      while ( 1 )
      {
        v84 = Elements;
        if ( (unsigned int)Elements >= v5->NumHistoryBuffers )
          break;
        v77 = 0;
        v89 = (unsigned int)Elements;
        HistoryBufferArray = v5->HistoryBufferArray;
        if ( CurrentThreadPreviousMode == 1 )
        {
          ULongFromUser = RtlReadULongFromUser(&HistoryBufferArray[(unsigned int)Elements]);
          v60 = ULongFromUser;
          v77 = ULongFromUser;
        }
        else
        {
          v60 = HistoryBufferArray[(unsigned int)Elements];
          v77 = HistoryBufferArray[(unsigned int)Elements];
        }
        v76 = (struct DXGCONTEXT *)(v86 + 8LL * (unsigned int)Elements);
        AllocationSafe = DXGPROCESS::GetAllocationSafe(v85, v88, v60);
        DXGALLOCATIONREFERENCE::MoveAssign(v76, AllocationSafe);
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v88);
        v62 = *(_QWORD *)v76;
        if ( !*(_QWORD *)v76 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1925;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Invalid history buffer handle provided to SubmitCommand. D3DKMT_HANDLE=0x%8x",
            v77,
            0,
            0,
            0,
            0);
          PagedPoolArray<VIDMM_MULTI_ALLOC *,16>::~PagedPoolArray<VIDMM_MULTI_ALLOC *,16>(&v95);
          PagedPoolArray<DXGALLOCATIONREFERENCE,16>::~PagedPoolArray<DXGALLOCATIONREFERENCE,16>(v98);
          COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v94);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
          DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
          DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
          ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
          if ( P != v73 && P )
            ExFreePoolWithTag(P, 0);
          P = 0;
          v74 = 0;
          DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
          if ( v69 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v54, EventProfilerExit, v55, v67);
          return 3221225485LL;
        }
        if ( *(_QWORD *)(v62 + 8) != *((_QWORD *)v7 + 2) )
        {
          _mm_lfence();
          WdLogSingleEntry3(
            2,
            *(_QWORD *)(v86 + 8 * v89),
            *(_QWORD *)(*(_QWORD *)(v86 + 8 * v89) + 8LL),
            *((_QWORD *)v7 + 2));
          WdLogGlobalForLineNumber = 1933;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"History buffer 0x%p device 0x%p does not match context device 0x%p.",
            *(_QWORD *)v76,
            *(_QWORD *)(*(_QWORD *)v76 + 8LL),
            *((_QWORD *)v7 + 2),
            0,
            0);
          PagedPoolArray<VIDMM_MULTI_ALLOC *,16>::~PagedPoolArray<VIDMM_MULTI_ALLOC *,16>(&v95);
          PagedPoolArray<DXGALLOCATIONREFERENCE,16>::~PagedPoolArray<DXGALLOCATIONREFERENCE,16>(v98);
          COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v94);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
          DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
          DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
          ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
          if ( P != v73 && P )
            ExFreePoolWithTag(P, 0);
          P = 0;
          v74 = 0;
          DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
          if ( v69 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v56, EventProfilerExit, v57, v67);
          return 3221225485LL;
        }
        v18[(unsigned int)Elements] = *(struct VIDMM_MULTI_ALLOC **)(v62 + 24);
        LODWORD(Elements) = Elements + 1;
      }
      v17 = (*(__int64 (__fastcall **)(struct VIDMM_MULTI_ALLOC **))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v90 + 16)
                                                                                           + 760LL)
                                                                               + 8LL)
                                                                   + 1032LL))(v18);
      if ( v17 >= 0 )
        goto LABEL_28;
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1970;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Invalid history buffer passed to SubmitCommand.",
        1970,
        0,
        0,
        0,
        0);
      PagedPoolArray<VIDMM_MULTI_ALLOC *,16>::~PagedPoolArray<VIDMM_MULTI_ALLOC *,16>(&v95);
      PagedPoolArray<DXGALLOCATIONREFERENCE,16>::~PagedPoolArray<DXGALLOCATIONREFERENCE,16>(v98);
      COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v94);
      DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
      DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
      DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
      ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
      if ( P != v73 && P )
        ExFreePoolWithTag(P, 0);
      goto LABEL_78;
    }
  }
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 1900;
  DxgkLogInternalTriageEvent(
    0,
    262145,
    -1,
    (unsigned int)L"Failed to created paged pool array for history buffer array",
    1900,
    Elements,
    Elements,
    Elements,
    Elements);
  PagedPoolArray<VIDMM_MULTI_ALLOC *,16>::~PagedPoolArray<VIDMM_MULTI_ALLOC *,16>(&v95);
  PagedPoolArray<DXGALLOCATIONREFERENCE,16>::~PagedPoolArray<DXGALLOCATIONREFERENCE,16>(v98);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v94);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v81);
  DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&void AcquireContextLock(DXGCONTEXT *),&void ReleaseContextLock(DXGCONTEXT *),4>(v91);
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
  ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE((ENSURE_CONTEXT_ARRAY_DEREFERENCE *)&v78);
  if ( P != v73 && P )
    ExFreePoolWithTag(P, 0);
  P = (PVOID)Elements;
  v74 = Elements;
  DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v75);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v67);
  v35 = v69 == (char)Elements;
LABEL_63:
  if ( !v35 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v33, EventProfilerExit, v34, v67);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14032cf7c  mov     [rsp+arg_10], rbx
0x14032cf81  mov     [rsp+arg_18], rsi
0x14032cf86  push    rdi
0x14032cf87  push    r12
0x14032cf89  push    r13
0x14032cf8b  push    r14
0x14032cf8d  push    r15
0x14032cf8f  sub     rsp, 4D0h
0x14032cf96  mov     rax, cs:__security_cookie
0x14032cf9d  xor     rax, rsp
0x14032cfa0  mov     [rsp+4F8h+var_38], rax
0x14032cfa8  mov     r12, rdx
0x14032cfab  mov     [rsp+4F8h+var_3F8], rdx
0x14032cfb3  mov     rsi, rcx
0x14032cfb6  mov     [rsp+4F8h+var_3E8], rdx
0x14032cfbe  mov     [rsp+4F8h+var_4A8], 0FFFFFFFFh
0x14032cfc6  xor     r13d, r13d
0x14032cfc9  mov     [rsp+4F8h+var_4A0], r13
0x14032cfce  mov     rax, cs:qword_1401604F0
0x14032cfd5  lea     r15d, [r13+2]
0x14032cfd9  lea     ebx, [r13+1]
0x14032cfdd  test    r15b, al
0x14032cfe0  jnz     short loc_14032CFE9
0x14032cfe2  mov     [rsp+4F8h+var_498], r13b
0x14032cfe7  jmp     short loc_14032D001
0x14032cfe9  mov     [rsp+4F8h+var_498], bl
0x14032cfed  mov     [rsp+4F8h+var_4A8], 836h
0x14032cff5  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x14032cffb  jnz     loc_14032DCCF
0x14032d001  mov     edx, 836h
0x14032d006  lea     rcx, [rsp+4F8h+var_4A8]
0x14032d00b  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14032d010  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14032d017  nop     dword ptr [rax+rax+00h]
0x14032d01c  mov     r14b, al
0x14032d01f  mov     [rsp+4F8h+var_490], al
0x14032d023  cmp     al, bl
0x14032d025  setz    [rsp+4F8h+var_48F]
0x14032d02a  xor     edx, edx; Val
0x14032d02c  mov     r8d, 180h; Size
0x14032d032  lea     rcx, [rsp+4F8h+var_1B8]; void *
0x14032d03a  call    memset
0x14032d03f  lea     rdi, [rsp+4F8h+var_1B8]
0x14032d047  cmp     r14b, bl
0x14032d04a  jz      loc_14032D518
0x14032d050  mov     rdi, rsi
0x14032d053  mov     edx, [rdi+0Ch]
0x14032d056  test    dl, 4
0x14032d059  jnz     loc_14032DCE6
0x14032d05f  mov     eax, [r12+198h]
0x14032d067  shr     eax, 8
0x14032d06a  test    bl, al
0x14032d06c  jnz     loc_14032DD5F
0x14032d072  mov     [rsp+4F8h+var_448], r13
0x14032d07a  mov     byte ptr [rsp+4F8h+var_4D0], bl; bool
0x14032d07e  mov     byte ptr [rsp+4F8h+var_4D8], r13b; bool
0x14032d083  lea     r9, [rsp+4F8h+var_448]; struct DXGCONTEXT **
0x14032d08b  mov     r8, r12; struct DXGPROCESS *
0x14032d08e  mov     edx, [rdi+1Ch]; unsigned int
0x14032d091  lea     rcx, [rsp+4F8h+var_458]; this
0x14032d099  call    ??0DXGCONTEXTBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGCONTEXT@@_N2@Z; DXGCONTEXTBYHANDLE::DXGCONTEXTBYHANDLE(uint,DXGPROCESS *,DXGCONTEXT * *,bool,bool)
0x14032d09e  mov     rsi, [rsp+4F8h+var_448]
0x14032d0a6  test    rsi, rsi
0x14032d0a9  jz      loc_14032DD6A
0x14032d0af  mov     eax, [rsi+188h]
0x14032d0b5  test    al, 10h
0x14032d0b7  jnz     loc_14032DDBD
0x14032d0bd  test    al, 8
0x14032d0bf  jnz     loc_14032DDF9
0x14032d0c5  mov     r14d, [rdi+18h]
0x14032d0c9  lea     eax, [r14-1]
0x14032d0cd  cmp     eax, 3Fh ; '?'
0x14032d0d0  ja      loc_14032E51C
0x14032d0d6  mov     eax, [rdi+12Ch]
0x14032d0dc  cmp     eax, 10h
0x14032d0df  ja      loc_14032DE19
0x14032d0e5  mov     rax, [rsi+10h]
0x14032d0e9  mov     rcx, [rax+10h]
0x14032d0ed  mov     rcx, [rcx+10h]
0x14032d0f1  cmp     [rcx+0D1h], r13b
0x14032d0f8  jnz     loc_14032D43F
0x14032d0fe  mov     rcx, r13
0x14032d101  mov     [rsp+4F8h+P], rcx
0x14032d106  mov     [rsp+4F8h+var_460], r13d
0x14032d10e  mov     r8d, r14d
0x14032d111  cmp     r14d, 4
0x14032d115  ja      loc_14032D4D6
0x14032d11b  lea     rax, [rsp+4F8h+var_480]
0x14032d120  mov     [rsp+4F8h+P], rax
0x14032d125  shl     r8, 3; Size
0x14032d129  xor     edx, edx; Val
0x14032d12b  lea     rcx, [rsp+4F8h+var_480]; void *
0x14032d130  call    memset
0x14032d135  mov     rcx, [rsp+4F8h+P]
0x14032d13a  mov     [rsp+4F8h+var_460], r14d
0x14032d142  mov     r9d, r14d
0x14032d145  test    rcx, rcx
0x14032d148  jz      loc_14032DE86
0x14032d14e  mov     [rsp+4F8h+var_438], rcx
0x14032d156  mov     [rsp+4F8h+var_430], r9d
0x14032d15e  prefetchw byte ptr [rsi+20h]
0x14032d162  mov     rax, [rsi+20h]
0x14032d166  test    rax, rax
0x14032d169  jz      loc_14032D3AD
0x14032d16f  lea     rcx, [rax+1]
0x14032d173  lock cmpxchg [rsi+20h], rcx
0x14032d179  jnz     short loc_14032D166
0x14032d17b  mov     rax, [rsp+4F8h+P]
0x14032d180  mov     [rax], rsi
0x14032d183  mov     rdx, [rsi+10h]; struct DXGDEVICE *
0x14032d187  lea     rcx, [rsp+4F8h+var_428]; this
0x14032d18f  call    ??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)
0x14032d194  mov     rdx, r12; struct DXGPROCESS *
0x14032d197  lea     rcx, [rsp+4F8h+var_390]; this
0x14032d19f  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x14032d1a4  mov     r9d, ebx
0x14032d1a7  mov     [rsp+4F8h+var_440], ebx
0x14032d1ae  or      r14d, 0FFFFFFFFh
0x14032d1b2  mov     r15d, 40000h
0x14032d1b8  cmp     r9d, [rdi+18h]
0x14032d1bc  jb      loc_14032D85F
0x14032d1c2  lea     rcx, [rsp+4F8h+var_390]; this
0x14032d1ca  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14032d1cf  mov     byte ptr [rsp+4F8h+var_4D8], bl
0x14032d1d3  mov     r8d, [rsp+4F8h+var_460]
0x14032d1db  mov     rdx, [rsp+4F8h+P]
0x14032d1e0  lea     rcx, [rsp+4F8h+var_3C8]
0x14032d1e8  call    ??0?$DXGPOINTERARRAYORDEREDACQUIRE@VDXGCONTEXT@@$1?AcquireContextLock@@YAXPEAV1@@Z$1?ReleaseContextLock@@YAX0@Z$03@@QEAA@PEAPEAVDXGCONTEXT@@IEE@Z; DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>::DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>(DXGCONTEXT * *,uint,uchar,uchar)
0x14032d1ed  xor     r13d, r13d
0x14032d1f0  cmp     [rsp+4F8h+var_398], r13b
0x14032d1f8  jnz     loc_14032D71A
0x14032d1fe  mov     r13, [rsi+10h]
0x14032d202  mov     [rsp+4F8h+var_3D0], r13
0x14032d20a  mov     rax, [r13+10h]
0x14032d20e  mov     rcx, [rax+10h]
0x14032d212  mov     [rsp+4F8h+var_410], rcx
0x14032d21a  mov     [rsp+4F8h+var_408], 0
0x14032d222  lea     rcx, [rsp+4F8h+var_418]; this
0x14032d22a  call    ?Acquire@DXGADAPTERSTOPRESETLOCKSHARED@@QEAAXXZ; DXGADAPTERSTOPRESETLOCKSHARED::Acquire(void)
0x14032d22f  mov     byte ptr [rsp+4F8h+var_4D8], 0
0x14032d234  xor     r8d, r8d
0x14032d237  mov     rdx, r13
0x14032d23a  lea     rcx, [rsp+4F8h+var_378]
0x14032d242  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x14032d247  xor     edx, edx; char *
0x14032d249  lea     rcx, [rsp+4F8h+var_378]; this
0x14032d251  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x14032d256  mov     r12d, eax
0x14032d259  xor     r13d, r13d
0x14032d25c  test    eax, eax
0x14032d25e  js      loc_14032D97D
0x14032d264  xor     r12d, r12d
0x14032d267  cmp     [rsi+1AEh], r12b
0x14032d26e  jz      loc_14032DA0E
0x14032d274  mov     [rsp+4F8h+var_248], r12
0x14032d27c  mov     [rsp+4F8h+var_1C0], r12d
0x14032d284  mov     [rsp+4F8h+var_2D8], r12
0x14032d28c  mov     [rsp+4F8h+var_250], r12d
0x14032d294  mov     edx, [rdi+170h]
0x14032d29a  test    edx, edx
0x14032d29c  jnz     loc_14032DF62
0x14032d2a2  cmp     [rdi+8], r12d
0x14032d2a6  jz      loc_14032E494
0x14032d2ac  mov     rcx, [rsp+4F8h+P]
0x14032d2b1  mov     al, [rsp+4F8h+var_48F]
0x14032d2b5  mov     byte ptr [rsp+4F8h+var_4C0], al; unsigned __int8
0x14032d2b9  mov     eax, [rdi+170h]
0x14032d2bf  mov     dword ptr [rsp+4F8h+var_4C8], eax; unsigned int
0x14032d2c3  mov     [rsp+4F8h+var_4D0], r13; struct VIDMM_MULTI_ALLOC **
0x14032d2c8  mov     [rsp+4F8h+var_4D8], rcx; struct DXGCONTEXT **
0x14032d2cd  lea     r9, [rsp+4F8h+var_418]; struct DXGADAPTERSTOPRESETLOCKSHARED *
0x14032d2d5  lea     r8, [rsp+4F8h+var_378]; struct COREDEVICEACCESS *
0x14032d2dd  mov     rdx, rdi; struct _D3DKMT_SUBMITCOMMAND *
0x14032d2e0  mov     rcx, rsi; this
0x14032d2e3  call    ?SubmitCommand@DXGCONTEXT@@QEAAJPEAU_D3DKMT_SUBMITCOMMAND@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAPEAV1@PEAPEAUVIDMM_MULTI_ALLOC@@IE@Z; DXGCONTEXT::SubmitCommand(_D3DKMT_SUBMITCOMMAND *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,DXGCONTEXT * *,VIDMM_MULTI_ALLOC * *,uint,uchar)
0x14032d2e8  mov     r14d, eax
0x14032d2eb  test    eax, eax
0x14032d2ed  jns     loc_14032D484
0x14032d2f3  lea     rax, [rsp+4F8h+var_2D0]
0x14032d2fb  mov     rcx, [rsp+4F8h+var_2D8]; void *
0x14032d303  cmp     rcx, rax
0x14032d306  jnz     loc_14032D435
0x14032d30c  lea     rcx, [rsp+4F8h+var_248]
0x14032d314  call    ??1?$PagedPoolArray@VDXGALLOCATIONREFERENCE@@$0BA@@@QEAA@XZ; PagedPoolArray<DXGALLOCATIONREFERENCE,16>::~PagedPoolArray<DXGALLOCATIONREFERENCE,16>(void)
0x14032d319  lea     rcx, [rsp+4F8h+var_378]; this
0x14032d321  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x14032d326  lea     rcx, [rsp+4F8h+var_418]; this
0x14032d32e  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x14032d333  lea     rcx, [rsp+4F8h+var_3C8]
0x14032d33b  call    ??1?$DXGPOINTERARRAYORDEREDACQUIRE@VDXGCONTEXT@@$1?AcquireContextLock@@YAXPEAV1@@Z$1?ReleaseContextLock@@YAX0@Z$03@@QEAA@XZ; DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>(void)
0x14032d340  lea     rcx, [rsp+4F8h+var_428]; this
0x14032d348  call    ??1DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@XZ; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL(void)
0x14032d34d  lea     rcx, [rsp+4F8h+var_438]; this
0x14032d355  call    ??1ENSURE_CONTEXT_ARRAY_DEREFERENCE@@QEAA@XZ; ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE(void)
0x14032d35a  lea     rax, [rsp+4F8h+var_480]
0x14032d35f  mov     rcx, [rsp+4F8h+P]; P
0x14032d364  cmp     rcx, rax
0x14032d367  jnz     loc_14032D4BA
0x14032d36d  mov     [rsp+4F8h+P], r12
0x14032d372  mov     [rsp+4F8h+var_460], r12d
0x14032d37a  lea     rcx, [rsp+4F8h+var_458]; this
0x14032d382  call    ??1DXGCONTEXTBYHANDLE@@QEAA@XZ; DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE(void)
0x14032d387  lea     rcx, [rsp+4F8h+var_4A8]; this
0x14032d38c  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14032d391  cmp     [rsp+4F8h+var_498], r12b
0x14032d396  jz      short loc_14032D3A4
0x14032d398  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x14032d39e  jnz     loc_14032E506
0x14032d3a4  mov     eax, r14d
0x14032d3a7  jmp     loc_14032E59F
0x14032d3ad  mov     rdx, rsi
0x14032d3b0  mov     ecx, r15d
0x14032d3b3  call    cs:__imp_WdLogSingleEntry1
0x14032d3ba  nop     dword ptr [rax+rax+00h]
0x14032d3bf  mov     cs:WdLogGlobalForLineNumber, 6E8h
0x14032d3c9  mov     [rsp+4F8h+var_4B8], r13
0x14032d3ce  mov     [rsp+4F8h+var_4C0], r13
0x14032d3d3  mov     [rsp+4F8h+var_4C8], r13
0x14032d3d8  mov     [rsp+4F8h+var_4D0], r13
0x14032d3dd  mov     [rsp+4F8h+var_4D8], rsi
0x14032d3e2  lea     r9, aDxgcontext0xPF; "DXGCONTEXT 0x%p failed to acquire refer"...
0x14032d3e9  or      r8d, 0FFFFFFFFh
0x14032d3ed  mov     edx, 40000h
0x14032d3f2  xor     ecx, ecx
0x14032d3f4  call    DxgkLogInternalTriageEvent
0x14032d3f9  lea     rcx, [rsp+4F8h+var_438]; this
0x14032d401  call    ??1ENSURE_CONTEXT_ARRAY_DEREFERENCE@@QEAA@XZ; ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE(void)
0x14032d406  lea     rax, [rsp+4F8h+var_480]
0x14032d40b  mov     rcx, [rsp+4F8h+P]; P
0x14032d410  cmp     rcx, rax
0x14032d413  jz      loc_14032D5D5
0x14032d419  test    rcx, rcx
0x14032d41c  jz      loc_14032D5D5
0x14032d422  xor     edx, edx; Tag
0x14032d424  call    cs:__imp_ExFreePoolWithTag
0x14032d42b  nop     dword ptr [rax+rax+00h]
0x14032d430  jmp     loc_14032D5D5
0x14032d435  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14032d43a  jmp     loc_14032D30C
0x14032d43f  add     rcx, 12B8h; this
0x14032d446  mov     r8, rdi; struct _D3DKMT_SUBMITCOMMAND *
0x14032d449  mov     rdx, r12; struct DXGPROCESS *
0x14032d44c  call    ?VmBusSendSubmitCommand@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAVDXGPROCESS@@PEAU_D3DKMT_SUBMITCOMMAND@@@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSubmitCommand(DXGPROCESS *,_D3DKMT_SUBMITCOMMAND *)
0x14032d451  mov     edi, eax
0x14032d453  lea     rcx, [rsp+4F8h+var_458]; this
0x14032d45b  call    ??1DXGCONTEXTBYHANDLE@@QEAA@XZ; DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE(void)
0x14032d460  lea     rcx, [rsp+4F8h+var_4A8]; this
0x14032d465  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14032d46a  cmp     [rsp+4F8h+var_498], r13b
0x14032d46f  jz      short loc_14032D47D
0x14032d471  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x14032d477  jnz     loc_14032DE70
0x14032d47d  mov     eax, edi
0x14032d47f  jmp     loc_14032E59F
0x14032d484  mov     r8d, [rdi+0Ch]
0x14032d488  shr     r8d, 1
0x14032d48b  and     r8d, ebx; int
0x14032d48e  jz      loc_14032E49C
0x14032d494  mov     rdx, [rdi+10h]; unsigned __int64
0x14032d498  test    rdx, rdx
0x14032d49b  jz      loc_14032D2F3
0x14032d4a1  mov     rcx, [rsp+4F8h+P]
0x14032d4a6  mov     eax, [rdi+18h]
0x14032d4a9  cmp     eax, ebx
0x14032d4ab  jbe     loc_14032E4CE
0x14032d4b1  add     rdi, 20h ; ' '
0x14032d4b5  jmp     loc_14032E4D1
0x14032d4ba  test    rcx, rcx
0x14032d4bd  jz      loc_14032D36D
0x14032d4c3  xor     edx, edx; Tag
0x14032d4c5  call    cs:__imp_ExFreePoolWithTag
0x14032d4cc  nop     dword ptr [rax+rax+00h]
0x14032d4d1  jmp     loc_14032D36D
0x14032d4d6  mov     r9d, r13d
0x14032d4d9  xor     edx, edx
0x14032d4db  or      rax, 0FFFFFFFFFFFFFFFFh
0x14032d4df  div     r8
0x14032d4e2  cmp     rax, 8
0x14032d4e6  jb      loc_14032D145
0x14032d4ec  lea     rdx, ds:0[r14*8]
0x14032d4f4  mov     ecx, 100h
0x14032d4f9  mov     r8d, 4B677844h
0x14032d4ff  call    cs:__imp_ExAllocatePool2
0x14032d506  nop     dword ptr [rax+rax+00h]
0x14032d50b  mov     rcx, rax
0x14032d50e  mov     [rsp+4F8h+P], rax
0x14032d513  jmp     loc_14032D13A
0x14032d518  mov     r8d, 180h; Size
0x14032d51e  mov     rdx, rsi; Src
0x14032d521  lea     rcx, [rsp+4F8h+var_1B8]; void *
0x14032d529  call    RtlCopyFromUser
0x14032d52e  jmp     loc_14032D053
0x14032d533  mov     r8, 0FFFFFFFFC000000Dh
0x14032d53a  mov     rbx, [rsp+4F8h+var_3E8]
0x14032d542  mov     rdx, rbx
0x14032d545  mov     ecx, 2
0x14032d54a  call    cs:__imp_WdLogSingleEntry2
0x14032d551  nop     dword ptr [rax+rax+00h]
0x14032d556  mov     cs:WdLogGlobalForLineNumber, 689h
0x14032d560  mov     [rsp+4F8h+var_4B8], 0
  ... truncated ...
```
