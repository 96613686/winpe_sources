# DxgkSubmitCommandInternal(_D3DKMT_SUBMITCOMMAND const *,DXGPROCESS *)

- ea: `0x14032620c`
- end: `0x14032785c`
- name: `?DxgkSubmitCommandInternal@@YAJPEBU_D3DKMT_SUBMITCOMMAND@@PEAVDXGPROCESS@@@Z`
- size: `5712`
- prototype: `__int64 __fastcall(const struct _D3DKMT_SUBMITCOMMAND *, struct DXGPROCESS *)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1401bf240`
- `0x1403257b0`

## callees

- `0x14000d7d0`
- `0x140012b14`
- `0x140013860`
- `0x1400158b0`
- `0x140015970`
- `0x140016330`
- `0x140016830`
- `0x140016b74`
- `0x140017fb8`
- `0x14001ab20`
- `0x14001b890`
- `0x14001baa0`
- `0x14001c320`
- `0x14001c660`
- `0x14001cbe0`
- `0x14001ccf0`
- `0x14001d0e4`
- `0x14001f120`
- `0x140020150`
- `0x14002ed70`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140191ea8`
- `0x1401e5400`
- `0x14024f688`
- `0x1403258d8`
- `0x14032620c`
- `0x140327b30`
- `0x140327c10`
- `0x140340d50`
- `0x140393544`
- `0x1403945a4`
- `0x140402b80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1403266b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326755`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326971`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326c64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326d5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326e58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326f25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140327303`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032743c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140327673`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403266b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326755`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326971`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326c64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326d5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326e58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140326f25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140327303`
- `ntoskrnl!ExFreePoolWithTag` at `0x14032743c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140327673`
- `ntoskrnl!ExAllocatePool2` at `0x14032678f`
- `ntoskrnl!ExAllocatePool2` at `0x14032678f`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x1403262a0`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x1403262a0`
- `watchdog!WdLogSingleEntry4` at `0x140326b84`
- `watchdog!WdLogSingleEntry4` at `0x1403270c1`
- `watchdog!WdLogSingleEntry4` at `0x1403277c7`
- `watchdog!WdLogSingleEntry4` at `0x140326b84`
- `watchdog!WdLogSingleEntry4` at `0x1403270c1`
- `watchdog!WdLogSingleEntry4` at `0x1403277c7`
- `watchdog!WdLogSingleEntry2` at `0x1403267da`
- `watchdog!WdLogSingleEntry2` at `0x1403275ac`
- `watchdog!WdLogSingleEntry2` at `0x1403267da`
- `watchdog!WdLogSingleEntry2` at `0x1403275ac`
- `watchdog!WdLogSingleEntry3` at `0x140326cb9`
- `watchdog!WdLogSingleEntry3` at `0x14032700b`
- `watchdog!WdLogSingleEntry3` at `0x140327373`
- `watchdog!WdLogSingleEntry3` at `0x140326cb9`
- `watchdog!WdLogSingleEntry3` at `0x14032700b`
- `watchdog!WdLogSingleEntry3` at `0x140327373`
- `watchdog!WdLogSingleEntry0` at `0x1403269bd`
- `watchdog!WdLogSingleEntry0` at `0x140326a8a`
- `watchdog!WdLogSingleEntry0` at `0x140326d99`
- `watchdog!WdLogSingleEntry0` at `0x140326e6e`
- `watchdog!WdLogSingleEntry0` at `0x140326f86`
- `watchdog!WdLogSingleEntry0` at `0x140326fa3`
- `watchdog!WdLogSingleEntry0` at `0x14032708e`
- `watchdog!WdLogSingleEntry0` at `0x14032711b`
- `watchdog!WdLogSingleEntry0` at `0x1403271a7`
- `watchdog!WdLogSingleEntry0` at `0x1403269bd`
- `watchdog!WdLogSingleEntry0` at `0x140326a8a`
- `watchdog!WdLogSingleEntry0` at `0x140326d99`
- `watchdog!WdLogSingleEntry0` at `0x140326e6e`
- `watchdog!WdLogSingleEntry0` at `0x140326f86`
- `watchdog!WdLogSingleEntry0` at `0x140326fa3`
- `watchdog!WdLogSingleEntry0` at `0x14032708e`
- `watchdog!WdLogSingleEntry0` at `0x14032711b`
- `watchdog!WdLogSingleEntry0` at `0x1403271a7`
- `watchdog!WdLogSingleEntry1` at `0x140326643`
- `watchdog!WdLogSingleEntry1` at `0x1403268ef`
- `watchdog!WdLogSingleEntry1` at `0x140327053`
- `watchdog!WdLogSingleEntry1` at `0x140327180`
- `watchdog!WdLogSingleEntry1` at `0x140327246`
- `watchdog!WdLogSingleEntry1` at `0x140326643`
- `watchdog!WdLogSingleEntry1` at `0x1403268ef`
- `watchdog!WdLogSingleEntry1` at `0x140327053`
- `watchdog!WdLogSingleEntry1` at `0x140327180`
- `watchdog!WdLogSingleEntry1` at `0x140327246`

## string_xrefs

- `0x14032707d`: `DXGCONTEXT 0x%p is hardware scheduled and should not be passed to SubmitCommandCb.`
- `0x140327196`: `DXGCONTEXT 0x%p is hardware scheduled and should not be passed to SubmitCommandCb.`
- `0x14032727e`: `Invalid history buffer handle provided to SubmitCommand. D3DKMT_HANDLE=0x%8x`
- `0x140326dcb`: `Invalid history buffer passed to SubmitCommand.`
- `0x140326e9e`: `Failed to created paged pool array for history buffer array`
- `0x140326f97`: `NoKmdAccess can be used only with testsigning`

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
  if ( (qword_14015C500 & 2) != 0 )
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
    v23 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSubmitCommand((DXG_GUEST_VIRTUALGPU_VMBUS *)(v10 + 4776), a2, v5);
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
0x14032620c  mov     [rsp+arg_10], rbx
0x140326211  mov     [rsp+arg_18], rsi
0x140326216  push    rdi
0x140326217  push    r12
0x140326219  push    r13
0x14032621b  push    r14
0x14032621d  push    r15
0x14032621f  sub     rsp, 4D0h
0x140326226  mov     rax, cs:__security_cookie
0x14032622d  xor     rax, rsp
0x140326230  mov     [rsp+4F8h+var_38], rax
0x140326238  mov     r12, rdx
0x14032623b  mov     [rsp+4F8h+var_3F8], rdx
0x140326243  mov     rsi, rcx
0x140326246  mov     [rsp+4F8h+var_3E8], rdx
0x14032624e  mov     [rsp+4F8h+var_4A8], 0FFFFFFFFh
0x140326256  xor     r13d, r13d
0x140326259  mov     [rsp+4F8h+var_4A0], r13
0x14032625e  mov     rax, cs:qword_14015C500
0x140326265  lea     r15d, [r13+2]
0x140326269  lea     ebx, [r13+1]
0x14032626d  test    r15b, al
0x140326270  jnz     short loc_140326279
0x140326272  mov     [rsp+4F8h+var_498], r13b
0x140326277  jmp     short loc_140326291
0x140326279  mov     [rsp+4F8h+var_498], bl
0x14032627d  mov     [rsp+4F8h+var_4A8], 836h
0x140326285  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x14032628b  jnz     loc_140326F5F
0x140326291  mov     edx, 836h
0x140326296  lea     rcx, [rsp+4F8h+var_4A8]
0x14032629b  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1403262a0  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x1403262a7  nop     dword ptr [rax+rax+00h]
0x1403262ac  mov     r14b, al
0x1403262af  mov     [rsp+4F8h+var_490], al
0x1403262b3  cmp     al, bl
0x1403262b5  setz    [rsp+4F8h+var_48F]
0x1403262ba  xor     edx, edx; Val
0x1403262bc  mov     r8d, 180h; Size
0x1403262c2  lea     rcx, [rsp+4F8h+var_1B8]; void *
0x1403262ca  call    memset
0x1403262cf  lea     rdi, [rsp+4F8h+var_1B8]
0x1403262d7  cmp     r14b, bl
0x1403262da  jz      loc_1403267A8
0x1403262e0  mov     rdi, rsi
0x1403262e3  mov     edx, [rdi+0Ch]
0x1403262e6  test    dl, 4
0x1403262e9  jnz     loc_140326F76
0x1403262ef  mov     eax, [r12+198h]
0x1403262f7  shr     eax, 8
0x1403262fa  test    bl, al
0x1403262fc  jnz     loc_140326FEF
0x140326302  mov     [rsp+4F8h+var_448], r13
0x14032630a  mov     byte ptr [rsp+4F8h+var_4D0], bl; bool
0x14032630e  mov     byte ptr [rsp+4F8h+var_4D8], r13b; bool
0x140326313  lea     r9, [rsp+4F8h+var_448]; struct DXGCONTEXT **
0x14032631b  mov     r8, r12; struct DXGPROCESS *
0x14032631e  mov     edx, [rdi+1Ch]; unsigned int
0x140326321  lea     rcx, [rsp+4F8h+var_458]; this
0x140326329  call    ??0DXGCONTEXTBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGCONTEXT@@_N2@Z; DXGCONTEXTBYHANDLE::DXGCONTEXTBYHANDLE(uint,DXGPROCESS *,DXGCONTEXT * *,bool,bool)
0x14032632e  mov     rsi, [rsp+4F8h+var_448]
0x140326336  test    rsi, rsi
0x140326339  jz      loc_140326FFA
0x14032633f  mov     eax, [rsi+188h]
0x140326345  test    al, 10h
0x140326347  jnz     loc_14032704D
0x14032634d  test    al, 8
0x14032634f  jnz     loc_140327089
0x140326355  mov     r14d, [rdi+18h]
0x140326359  lea     eax, [r14-1]
0x14032635d  cmp     eax, 3Fh ; '?'
0x140326360  ja      loc_1403277AC
0x140326366  mov     eax, [rdi+12Ch]
0x14032636c  cmp     eax, 10h
0x14032636f  ja      loc_1403270A9
0x140326375  mov     rax, [rsi+10h]
0x140326379  mov     rcx, [rax+10h]
0x14032637d  mov     rcx, [rcx+10h]
0x140326381  cmp     [rcx+0D1h], r13b
0x140326388  jnz     loc_1403266CF
0x14032638e  mov     rcx, r13
0x140326391  mov     [rsp+4F8h+P], rcx
0x140326396  mov     [rsp+4F8h+var_460], r13d
0x14032639e  mov     r8d, r14d
0x1403263a1  cmp     r14d, 4
0x1403263a5  ja      loc_140326766
0x1403263ab  lea     rax, [rsp+4F8h+var_480]
0x1403263b0  mov     [rsp+4F8h+P], rax
0x1403263b5  shl     r8, 3; Size
0x1403263b9  xor     edx, edx; Val
0x1403263bb  lea     rcx, [rsp+4F8h+var_480]; void *
0x1403263c0  call    memset
0x1403263c5  mov     rcx, [rsp+4F8h+P]
0x1403263ca  mov     [rsp+4F8h+var_460], r14d
0x1403263d2  mov     r9d, r14d
0x1403263d5  test    rcx, rcx
0x1403263d8  jz      loc_140327116
0x1403263de  mov     [rsp+4F8h+var_438], rcx
0x1403263e6  mov     [rsp+4F8h+var_430], r9d
0x1403263ee  prefetchw byte ptr [rsi+20h]
0x1403263f2  mov     rax, [rsi+20h]
0x1403263f6  test    rax, rax
0x1403263f9  jz      loc_14032663D
0x1403263ff  lea     rcx, [rax+1]
0x140326403  lock cmpxchg [rsi+20h], rcx
0x140326409  jnz     short loc_1403263F6
0x14032640b  mov     rax, [rsp+4F8h+P]
0x140326410  mov     [rax], rsi
0x140326413  mov     rdx, [rsi+10h]; struct DXGDEVICE *
0x140326417  lea     rcx, [rsp+4F8h+var_428]; this
0x14032641f  call    ??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)
0x140326424  mov     rdx, r12; struct DXGPROCESS *
0x140326427  lea     rcx, [rsp+4F8h+var_390]; this
0x14032642f  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x140326434  mov     r9d, ebx
0x140326437  mov     [rsp+4F8h+var_440], ebx
0x14032643e  or      r14d, 0FFFFFFFFh
0x140326442  mov     r15d, 40000h
0x140326448  cmp     r9d, [rdi+18h]
0x14032644c  jb      loc_140326AEF
0x140326452  lea     rcx, [rsp+4F8h+var_390]; this
0x14032645a  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14032645f  mov     byte ptr [rsp+4F8h+var_4D8], bl
0x140326463  mov     r8d, [rsp+4F8h+var_460]
0x14032646b  mov     rdx, [rsp+4F8h+P]
0x140326470  lea     rcx, [rsp+4F8h+var_3C8]
0x140326478  call    ??0?$DXGPOINTERARRAYORDEREDACQUIRE@VDXGCONTEXT@@$1?AcquireContextLock@@YAXPEAV1@@Z$1?ReleaseContextLock@@YAX0@Z$03@@QEAA@PEAPEAVDXGCONTEXT@@IEE@Z; DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>::DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>(DXGCONTEXT * *,uint,uchar,uchar)
0x14032647d  xor     r13d, r13d
0x140326480  cmp     [rsp+4F8h+var_398], r13b
0x140326488  jnz     loc_1403269AA
0x14032648e  mov     r13, [rsi+10h]
0x140326492  mov     [rsp+4F8h+var_3D0], r13
0x14032649a  mov     rax, [r13+10h]
0x14032649e  mov     rcx, [rax+10h]
0x1403264a2  mov     [rsp+4F8h+var_410], rcx
0x1403264aa  mov     [rsp+4F8h+var_408], 0
0x1403264b2  lea     rcx, [rsp+4F8h+var_418]; this
0x1403264ba  call    ?Acquire@DXGADAPTERSTOPRESETLOCKSHARED@@QEAAXXZ; DXGADAPTERSTOPRESETLOCKSHARED::Acquire(void)
0x1403264bf  mov     byte ptr [rsp+4F8h+var_4D8], 0
0x1403264c4  xor     r8d, r8d
0x1403264c7  mov     rdx, r13
0x1403264ca  lea     rcx, [rsp+4F8h+var_378]
0x1403264d2  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x1403264d7  xor     edx, edx; char *
0x1403264d9  lea     rcx, [rsp+4F8h+var_378]; this
0x1403264e1  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x1403264e6  mov     r12d, eax
0x1403264e9  xor     r13d, r13d
0x1403264ec  test    eax, eax
0x1403264ee  js      loc_140326C0D
0x1403264f4  xor     r12d, r12d
0x1403264f7  cmp     [rsi+1AEh], r12b
0x1403264fe  jz      loc_140326C9E
0x140326504  mov     [rsp+4F8h+var_248], r12
0x14032650c  mov     [rsp+4F8h+var_1C0], r12d
0x140326514  mov     [rsp+4F8h+var_2D8], r12
0x14032651c  mov     [rsp+4F8h+var_250], r12d
0x140326524  mov     edx, [rdi+170h]
0x14032652a  test    edx, edx
0x14032652c  jnz     loc_1403271F2
0x140326532  cmp     [rdi+8], r12d
0x140326536  jz      loc_140327724
0x14032653c  mov     rcx, [rsp+4F8h+P]
0x140326541  mov     al, [rsp+4F8h+var_48F]
0x140326545  mov     byte ptr [rsp+4F8h+var_4C0], al; unsigned __int8
0x140326549  mov     eax, [rdi+170h]
0x14032654f  mov     dword ptr [rsp+4F8h+var_4C8], eax; unsigned int
0x140326553  mov     [rsp+4F8h+var_4D0], r13; struct VIDMM_MULTI_ALLOC **
0x140326558  mov     [rsp+4F8h+var_4D8], rcx; struct DXGCONTEXT **
0x14032655d  lea     r9, [rsp+4F8h+var_418]; struct DXGADAPTERSTOPRESETLOCKSHARED *
0x140326565  lea     r8, [rsp+4F8h+var_378]; struct COREDEVICEACCESS *
0x14032656d  mov     rdx, rdi; struct _D3DKMT_SUBMITCOMMAND *
0x140326570  mov     rcx, rsi; this
0x140326573  call    ?SubmitCommand@DXGCONTEXT@@QEAAJPEAU_D3DKMT_SUBMITCOMMAND@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAPEAV1@PEAPEAUVIDMM_MULTI_ALLOC@@IE@Z; DXGCONTEXT::SubmitCommand(_D3DKMT_SUBMITCOMMAND *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,DXGCONTEXT * *,VIDMM_MULTI_ALLOC * *,uint,uchar)
0x140326578  mov     r14d, eax
0x14032657b  test    eax, eax
0x14032657d  jns     loc_140326714
0x140326583  lea     rax, [rsp+4F8h+var_2D0]
0x14032658b  mov     rcx, [rsp+4F8h+var_2D8]; void *
0x140326593  cmp     rcx, rax
0x140326596  jnz     loc_1403266C5
0x14032659c  lea     rcx, [rsp+4F8h+var_248]
0x1403265a4  call    ??1?$PagedPoolArray@VDXGALLOCATIONREFERENCE@@$0BA@@@QEAA@XZ; PagedPoolArray<DXGALLOCATIONREFERENCE,16>::~PagedPoolArray<DXGALLOCATIONREFERENCE,16>(void)
0x1403265a9  lea     rcx, [rsp+4F8h+var_378]; this
0x1403265b1  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1403265b6  lea     rcx, [rsp+4F8h+var_418]; this
0x1403265be  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403265c3  lea     rcx, [rsp+4F8h+var_3C8]
0x1403265cb  call    ??1?$DXGPOINTERARRAYORDEREDACQUIRE@VDXGCONTEXT@@$1?AcquireContextLock@@YAXPEAV1@@Z$1?ReleaseContextLock@@YAX0@Z$03@@QEAA@XZ; DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>::~DXGPOINTERARRAYORDEREDACQUIRE<DXGCONTEXT,&AcquireContextLock(DXGCONTEXT *),&ReleaseContextLock(DXGCONTEXT *),4>(void)
0x1403265d0  lea     rcx, [rsp+4F8h+var_428]; this
0x1403265d8  call    ??1DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@XZ; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL(void)
0x1403265dd  lea     rcx, [rsp+4F8h+var_438]; this
0x1403265e5  call    ??1ENSURE_CONTEXT_ARRAY_DEREFERENCE@@QEAA@XZ; ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE(void)
0x1403265ea  lea     rax, [rsp+4F8h+var_480]
0x1403265ef  mov     rcx, [rsp+4F8h+P]; P
0x1403265f4  cmp     rcx, rax
0x1403265f7  jnz     loc_14032674A
0x1403265fd  mov     [rsp+4F8h+P], r12
0x140326602  mov     [rsp+4F8h+var_460], r12d
0x14032660a  lea     rcx, [rsp+4F8h+var_458]; this
0x140326612  call    ??1DXGCONTEXTBYHANDLE@@QEAA@XZ; DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE(void)
0x140326617  lea     rcx, [rsp+4F8h+var_4A8]; this
0x14032661c  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140326621  cmp     [rsp+4F8h+var_498], r12b
0x140326626  jz      short loc_140326634
0x140326628  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x14032662e  jnz     loc_140327796
0x140326634  mov     eax, r14d
0x140326637  jmp     loc_14032782F
0x14032663d  mov     rdx, rsi
0x140326640  mov     ecx, r15d
0x140326643  call    cs:__imp_WdLogSingleEntry1
0x14032664a  nop     dword ptr [rax+rax+00h]
0x14032664f  mov     cs:WdLogGlobalForLineNumber, 6E8h
0x140326659  mov     [rsp+4F8h+var_4B8], r13
0x14032665e  mov     [rsp+4F8h+var_4C0], r13
0x140326663  mov     [rsp+4F8h+var_4C8], r13
0x140326668  mov     [rsp+4F8h+var_4D0], r13
0x14032666d  mov     [rsp+4F8h+var_4D8], rsi
0x140326672  lea     r9, aDxgcontext0xPF; "DXGCONTEXT 0x%p failed to acquire refer"...
0x140326679  or      r8d, 0FFFFFFFFh
0x14032667d  mov     edx, 40000h
0x140326682  xor     ecx, ecx
0x140326684  call    DxgkLogInternalTriageEvent
0x140326689  lea     rcx, [rsp+4F8h+var_438]; this
0x140326691  call    ??1ENSURE_CONTEXT_ARRAY_DEREFERENCE@@QEAA@XZ; ENSURE_CONTEXT_ARRAY_DEREFERENCE::~ENSURE_CONTEXT_ARRAY_DEREFERENCE(void)
0x140326696  lea     rax, [rsp+4F8h+var_480]
0x14032669b  mov     rcx, [rsp+4F8h+P]; P
0x1403266a0  cmp     rcx, rax
0x1403266a3  jz      loc_140326865
0x1403266a9  test    rcx, rcx
0x1403266ac  jz      loc_140326865
0x1403266b2  xor     edx, edx; Tag
0x1403266b4  call    cs:__imp_ExFreePoolWithTag
0x1403266bb  nop     dword ptr [rax+rax+00h]
0x1403266c0  jmp     loc_140326865
0x1403266c5  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1403266ca  jmp     loc_14032659C
0x1403266cf  add     rcx, 12A8h; this
0x1403266d6  mov     r8, rdi; struct _D3DKMT_SUBMITCOMMAND *
0x1403266d9  mov     rdx, r12; struct DXGPROCESS *
0x1403266dc  call    ?VmBusSendSubmitCommand@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAVDXGPROCESS@@PEAU_D3DKMT_SUBMITCOMMAND@@@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSubmitCommand(DXGPROCESS *,_D3DKMT_SUBMITCOMMAND *)
0x1403266e1  mov     edi, eax
0x1403266e3  lea     rcx, [rsp+4F8h+var_458]; this
0x1403266eb  call    ??1DXGCONTEXTBYHANDLE@@QEAA@XZ; DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE(void)
0x1403266f0  lea     rcx, [rsp+4F8h+var_4A8]; this
0x1403266f5  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1403266fa  cmp     [rsp+4F8h+var_498], r13b
0x1403266ff  jz      short loc_14032670D
0x140326701  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x140326707  jnz     loc_140327100
0x14032670d  mov     eax, edi
0x14032670f  jmp     loc_14032782F
0x140326714  mov     r8d, [rdi+0Ch]
0x140326718  shr     r8d, 1
0x14032671b  and     r8d, ebx; int
0x14032671e  jz      loc_14032772C
0x140326724  mov     rdx, [rdi+10h]; unsigned __int64
0x140326728  test    rdx, rdx
0x14032672b  jz      loc_140326583
0x140326731  mov     rcx, [rsp+4F8h+P]
0x140326736  mov     eax, [rdi+18h]
0x140326739  cmp     eax, ebx
0x14032673b  jbe     loc_14032775E
0x140326741  add     rdi, 20h ; ' '
0x140326745  jmp     loc_140327761
0x14032674a  test    rcx, rcx
0x14032674d  jz      loc_1403265FD
0x140326753  xor     edx, edx; Tag
0x140326755  call    cs:__imp_ExFreePoolWithTag
0x14032675c  nop     dword ptr [rax+rax+00h]
0x140326761  jmp     loc_1403265FD
0x140326766  mov     r9d, r13d
0x140326769  xor     edx, edx
0x14032676b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14032676f  div     r8
0x140326772  cmp     rax, 8
0x140326776  jb      loc_1403263D5
0x14032677c  lea     rdx, ds:0[r14*8]
0x140326784  mov     ecx, 100h
0x140326789  mov     r8d, 4B677844h
0x14032678f  call    cs:__imp_ExAllocatePool2
0x140326796  nop     dword ptr [rax+rax+00h]
0x14032679b  mov     rcx, rax
0x14032679e  mov     [rsp+4F8h+P], rax
0x1403267a3  jmp     loc_1403263CA
0x1403267a8  mov     r8d, 180h; Size
0x1403267ae  mov     rdx, rsi; Src
0x1403267b1  lea     rcx, [rsp+4F8h+var_1B8]; void *
0x1403267b9  call    RtlCopyFromUser
0x1403267be  jmp     loc_1403262E3
0x1403267c3  mov     r8, 0FFFFFFFFC000000Dh
0x1403267ca  mov     rbx, [rsp+4F8h+var_3E8]
0x1403267d2  mov     rdx, rbx
0x1403267d5  mov     ecx, 2
0x1403267da  call    cs:__imp_WdLogSingleEntry2
0x1403267e1  nop     dword ptr [rax+rax+00h]
0x1403267e6  mov     cs:WdLogGlobalForLineNumber, 689h
0x1403267f0  mov     [rsp+4F8h+var_4B8], 0
  ... truncated ...
```
