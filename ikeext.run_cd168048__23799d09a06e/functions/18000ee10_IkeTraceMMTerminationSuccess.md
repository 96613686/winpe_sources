# IkeTraceMMTerminationSuccess

- ea: `0x18000ee10`
- end: `0x18000f9f0`
- name: `IkeTraceMMTerminationSuccess`
- size: `3040`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eb14`

## callees

- `0x1800061ec`
- `0x180008310`
- `0x180008388`
- `0x18000eb64`
- `0x18000edf0`
- `0x18000ee10`
- `0x180010680`
- `0x180010770`
- `0x180010db0`
- `0x180016534`
- `0x18004882c`
- `0x180050850`
- `0x18005390c`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000ee64`
- `ntdll!EtwEventEnabled` at `0x18000ee64`
- `ntdll!EtwEventWrite` at `0x18000f2f2`
- `ntdll!EtwEventWrite` at `0x18000f2f2`
- `ntdll!EtwEventActivityIdControl` at `0x18000eef0`
- `ntdll!EtwEventActivityIdControl` at `0x18000f31b`
- `ntdll!EtwEventActivityIdControl` at `0x18000f5e6`
- `ntdll!EtwEventActivityIdControl` at `0x18000eef0`
- `ntdll!EtwEventActivityIdControl` at `0x18000f31b`
- `ntdll!EtwEventActivityIdControl` at `0x18000f5e6`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f5be`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f670`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f72a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f7e6`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f89f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f930`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f9c1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f5be`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f670`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f72a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f7e6`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f89f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f930`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f9c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eea3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000efae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f09e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f132`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f1ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f228`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f358`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f384`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f3b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f45f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f48b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eea3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000efae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f09e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f132`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f1ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f228`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f358`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f384`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f3b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f45f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f48b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4e3`

## string_xrefs

- `0x18000f300`: `IkeWriteEvent`
- `0x18000f9d9`: `EtwEventWrite`

## pseudocode

```c
__int64 __fastcall IkeTraceMMTerminationSuccess(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int *v3; // rbx
  __int64 v4; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r11
  int IPVersion; // eax
  __int64 v10; // rcx
  unsigned int v11; // r14d
  int v12; // eax
  _DWORD *v13; // rax
  __int64 v14; // rcx
  _DWORD *v15; // rsi
  __int64 v16; // rdi
  __int64 v17; // r11
  __int64 v18; // rcx
  __int128 *v19; // r14
  int v20; // eax
  _DWORD *v21; // rax
  __int64 v22; // rcx
  _DWORD *v23; // rsi
  __int64 v24; // rdi
  __int64 v25; // rcx
  int v26; // r14d
  int v27; // eax
  _DWORD *v28; // rax
  __int64 v29; // rcx
  _DWORD *v30; // rsi
  __int64 v31; // rdi
  __int64 v32; // rcx
  __int64 v33; // r14
  int v34; // eax
  _QWORD *v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // rsi
  __int64 v38; // rdi
  __int64 v39; // rcx
  __int64 v40; // r14
  int v41; // eax
  _QWORD *v42; // rax
  __int64 v43; // rcx
  _QWORD *v44; // rsi
  __int64 v45; // rdi
  __int64 v46; // rcx
  __int64 v47; // r14
  int v48; // eax
  _QWORD *v49; // rax
  __int64 v50; // rcx
  _QWORD *v51; // rsi
  __int64 v52; // rdi
  __int64 v53; // rdi
  unsigned int v54; // eax
  __int64 v55; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rax
  const char *v68; // rdx
  __int64 v69; // rax
  const char *v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rax
  const char *v73; // rdx
  __int64 v74; // rax
  __int64 v75; // rax
  const char *v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rax
  const char *v79; // rdx
  __int64 v80; // rax
  const char *v81; // rdx
  __int64 v82; // rax
  const char *v83; // rdx
  unsigned int v84; // [rsp+20h] [rbp-59h] BYREF
  __int128 *v85; // [rsp+28h] [rbp-51h] BYREF
  __int64 v86; // [rsp+30h] [rbp-49h]
  unsigned int *v87; // [rsp+38h] [rbp-41h] BYREF
  __int128 v88; // [rsp+40h] [rbp-39h] BYREF
  _WORD v89[16]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v90; // [rsp+70h] [rbp-9h] BYREF

  v86 = a1;
  v90 = 0;
  v2 = 0;
  v3 = 0;
  if ( !(unsigned __int8)WfpIsTraceEnabled()
    || !(unsigned __int8)EtwEventEnabled(WfpEventTraceHandle, WFP_MM_TERMINATION_SUCCESS_V1) )
  {
    goto LABEL_73;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v4);
  if ( !IsEnabledDeviceUsageNoInline )
  {
    v6 = (unsigned int *)HeapAlloc(gWfpHeap, 8u, 0x3D0u);
    v3 = v6;
    if ( v6 )
    {
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v6));
      goto LABEL_9;
    }
    v67 = WfpReportSysErrorAsNtStatus(v7, "HeapAlloc", 3221225495LL);
    v2 = v67;
    if ( !v67 )
      goto LABEL_9;
    v68 = "WfpMemAlloc";
LABEL_100:
    WfpReportError(v67, v68);
    goto LABEL_9;
  }
  v3 = (unsigned int *)HeapAlloc(gWfpHeap, 8u, 0x3D0u);
  if ( !v3 )
  {
    v67 = WfpReportSysErrorAsNtStatus(v59, "HeapAlloc", 3221225495LL);
    v2 = v67;
    if ( !v67 )
      goto LABEL_9;
    v68 = "WfpMemAlloc25B";
    goto LABEL_100;
  }
  if ( gWfpTrackHeapAllocs )
    _InterlockedIncrement(&gWfpNumHeapAllocs);
LABEL_9:
  v2 = IkeReturnError(v2, "IkeAllocateTraceParams");
  if ( v2 )
    goto LABEL_73;
  EtwEventActivityIdControl(1, &v90);
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *((_QWORD *)&v88 + 1) = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&v88 = a1;
    EtwEventActivityIdControl(2, &v88);
  }
  v87 = 0;
  memset(v89, 0, 28);
  v88 = 0;
  IkeAddrGetAddrBytes(a1 + 376, &v87, &v84);
  IPVersion = IkeAddrGetIPVersion(v8);
  v10 = 28;
  v84 = 28;
  if ( IPVersion )
  {
    memset(v89, 0, 28);
    v89[0] = 23;
    v85 = (__int128 *)v89;
    v11 = 28;
    *(_OWORD *)&v89[4] = *(_OWORD *)v87;
  }
  else
  {
    v11 = 16;
    v88 = 0;
    LOWORD(v88) = 2;
    v85 = &v88;
    v10 = *v87;
    DWORD1(v88) = *v87;
  }
  v3[1] += 4;
  if ( v3[1] >= 0x2000 )
  {
    v16 = WfpReportSysErrorAsWinError(v10, "IkeTraceUInt32", 122, 1);
    goto LABEL_23;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v12 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v12 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v10);
  if ( v12 )
  {
    v15 = HeapAlloc(gWfpHeap, 0, 4u);
    if ( v15 )
    {
      v16 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
      goto LABEL_21;
    }
    v69 = WfpReportSysErrorAsNtStatus(v57, "HeapAlloc", 3221225495LL);
    v16 = v69;
    if ( v69 )
    {
      v70 = "WfpMemAlloc25B";
LABEL_107:
      WfpReportError(v69, v70);
    }
  }
  else
  {
    v13 = HeapAlloc(gWfpHeap, 0, 4u);
    v15 = v13;
    if ( v13 )
    {
      v16 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v13));
      goto LABEL_21;
    }
    v69 = WfpReportSysErrorAsNtStatus(v14, "HeapAlloc", 3221225495LL);
    v16 = v69;
    if ( v69 )
    {
      v70 = "WfpMemAlloc";
      goto LABEL_107;
    }
  }
LABEL_21:
  if ( !v16 )
  {
    IkePushTraceAlloc(v3, v15);
    *v15 = v11;
    v71 = 2LL * *v3;
    *(_QWORD *)&v3[2 * v71 + 2] = v15;
    *(_QWORD *)&v3[2 * v71 + 4] = 4;
    ++*v3;
  }
LABEL_23:
  IkeReturnError(v16, "IkeTraceUInt32");
  IkeTraceBytes(v3, v85, v11, 1);
  v85 = 0;
  memset(v89, 0, 28);
  v88 = 0;
  IkeAddrGetAddrBytes(v86 + 436, &v85, &v87);
  if ( (unsigned int)IkeAddrGetIPVersion(v17 + 436) )
  {
    memset(v89, 0, 28);
    v19 = (__int128 *)v89;
    v89[0] = 23;
    *(_OWORD *)&v89[4] = *v85;
  }
  else
  {
    v88 = 0;
    v84 = 16;
    LOWORD(v88) = 2;
    v19 = &v88;
    v18 = *(unsigned int *)v85;
    DWORD1(v88) = *(_DWORD *)v85;
  }
  v3[1] += 4;
  if ( v3[1] >= 0x2000 )
  {
    v24 = WfpReportSysErrorAsWinError(v18, "IkeTraceUInt32", 122, 1);
    goto LABEL_34;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v20 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v20 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v18);
  if ( v20 )
  {
    v23 = HeapAlloc(gWfpHeap, 0, 4u);
    if ( v23 )
    {
      v24 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
      goto LABEL_32;
    }
    v72 = WfpReportSysErrorAsNtStatus(v58, "HeapAlloc", 3221225495LL);
    v24 = v72;
    if ( v72 )
    {
      v73 = "WfpMemAlloc25B";
LABEL_114:
      WfpReportError(v72, v73);
    }
  }
  else
  {
    v21 = HeapAlloc(gWfpHeap, 0, 4u);
    v23 = v21;
    if ( v21 )
    {
      v24 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v21));
      goto LABEL_32;
    }
    v72 = WfpReportSysErrorAsNtStatus(v22, "HeapAlloc", 3221225495LL);
    v24 = v72;
    if ( v72 )
    {
      v73 = "WfpMemAlloc";
      goto LABEL_114;
    }
  }
LABEL_32:
  if ( !v24 )
  {
    IkePushTraceAlloc(v3, v23);
    *v23 = v84;
    v74 = 2LL * *v3;
    *(_QWORD *)&v3[2 * v74 + 2] = v23;
    *(_QWORD *)&v3[2 * v74 + 4] = 4;
    ++*v3;
  }
LABEL_34:
  IkeReturnError(v24, "IkeTraceUInt32");
  IkeTraceBytes(v3, v19, v84, 1);
  v26 = *(_DWORD *)(v86 + 584);
  v3[1] += 4;
  if ( v3[1] >= 0x2000 )
  {
    v31 = WfpReportSysErrorAsWinError(v25, "IkeTraceUInt32", 122, 1);
    goto LABEL_43;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v27 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v27 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v25);
  if ( v27 )
  {
    v30 = HeapAlloc(gWfpHeap, 0, 4u);
    if ( v30 )
    {
      v31 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
      goto LABEL_41;
    }
    v75 = WfpReportSysErrorAsNtStatus(v66, "HeapAlloc", 3221225495LL);
    v31 = v75;
    if ( v75 )
    {
      v76 = "WfpMemAlloc25B";
LABEL_121:
      WfpReportError(v75, v76);
    }
  }
  else
  {
    v28 = HeapAlloc(gWfpHeap, 0, 4u);
    v30 = v28;
    if ( v28 )
    {
      v31 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v28));
      goto LABEL_41;
    }
    v75 = WfpReportSysErrorAsNtStatus(v29, "HeapAlloc", 3221225495LL);
    v31 = v75;
    if ( v75 )
    {
      v76 = "WfpMemAlloc";
      goto LABEL_121;
    }
  }
LABEL_41:
  if ( !v31 )
  {
    IkePushTraceAlloc(v3, v30);
    *v30 = v26;
    v77 = 2LL * *v3;
    *(_QWORD *)&v3[2 * v77 + 2] = v30;
    *(_QWORD *)&v3[2 * v77 + 4] = 4;
    ++*v3;
  }
LABEL_43:
  IkeReturnError(v31, "IkeTraceUInt32");
  v33 = *(_QWORD *)(v86 + 992);
  v3[1] += 8;
  if ( v3[1] >= 0x2000 )
  {
    v38 = WfpReportSysErrorAsWinError(v32, "IkeTraceUInt64", 122, 1);
    goto LABEL_52;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v34 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v34 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v32);
  if ( v34 )
  {
    v37 = HeapAlloc(gWfpHeap, 0, 8u);
    if ( v37 )
    {
      v38 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
      goto LABEL_50;
    }
    v78 = WfpReportSysErrorAsNtStatus(v63, "HeapAlloc", 3221225495LL);
    v38 = v78;
    if ( v78 )
    {
      v79 = "WfpMemAlloc25B";
LABEL_128:
      WfpReportError(v78, v79);
    }
  }
  else
  {
    v35 = HeapAlloc(gWfpHeap, 0, 8u);
    v37 = v35;
    if ( v35 )
    {
      v38 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v35));
      goto LABEL_50;
    }
    v78 = WfpReportSysErrorAsNtStatus(v36, "HeapAlloc", 3221225495LL);
    v38 = v78;
    if ( v78 )
    {
      v79 = "WfpMemAlloc";
      goto LABEL_128;
    }
  }
LABEL_50:
  if ( !v38 )
  {
    IkePushTraceAlloc(v3, v37);
    *v37 = v33;
    v60 = 2LL * *v3;
    *(_QWORD *)&v3[2 * v60 + 2] = v37;
    *(_QWORD *)&v3[2 * v60 + 4] = 8;
    ++*v3;
  }
LABEL_52:
  IkeReturnError(v38, "IkeTraceUInt64");
  v40 = *(_QWORD *)(v86 + 680);
  v3[1] += 8;
  if ( v3[1] >= 0x2000 )
  {
    v45 = WfpReportSysErrorAsWinError(v39, "IkeTraceUInt64", 122, 1);
    goto LABEL_61;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v41 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v41 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v39);
  if ( v41 )
  {
    v44 = HeapAlloc(gWfpHeap, 0, 8u);
    if ( v44 )
    {
      v45 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
      goto LABEL_59;
    }
    v80 = WfpReportSysErrorAsNtStatus(v64, "HeapAlloc", 3221225495LL);
    v45 = v80;
    if ( v80 )
    {
      v81 = "WfpMemAlloc25B";
LABEL_135:
      WfpReportError(v80, v81);
    }
  }
  else
  {
    v42 = HeapAlloc(gWfpHeap, 0, 8u);
    v44 = v42;
    if ( v42 )
    {
      v45 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v42));
      goto LABEL_59;
    }
    v80 = WfpReportSysErrorAsNtStatus(v43, "HeapAlloc", 3221225495LL);
    v45 = v80;
    if ( v80 )
    {
      v81 = "WfpMemAlloc";
      goto LABEL_135;
    }
  }
LABEL_59:
  if ( !v45 )
  {
    IkePushTraceAlloc(v3, v44);
    *v44 = v40;
    v61 = 2LL * *v3;
    *(_QWORD *)&v3[2 * v61 + 2] = v44;
    *(_QWORD *)&v3[2 * v61 + 4] = 8;
    ++*v3;
  }
LABEL_61:
  IkeReturnError(v45, "IkeTraceUInt64");
  v47 = *(_QWORD *)(v86 + 688);
  v3[1] += 8;
  if ( v3[1] < 0x2000 )
  {
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      v48 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      v48 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v46);
    if ( v48 )
    {
      v51 = HeapAlloc(gWfpHeap, 0, 8u);
      if ( v51 )
      {
        v52 = 0;
        if ( gWfpTrackHeapAllocs )
          _InterlockedIncrement(&gWfpNumHeapAllocs);
        goto LABEL_68;
      }
      v82 = WfpReportSysErrorAsNtStatus(v65, "HeapAlloc", 3221225495LL);
      v52 = v82;
      if ( v82 )
      {
        v83 = "WfpMemAlloc25B";
LABEL_142:
        WfpReportError(v82, v83);
      }
    }
    else
    {
      v49 = HeapAlloc(gWfpHeap, 0, 8u);
      v51 = v49;
      if ( v49 )
      {
        v52 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v49));
        goto LABEL_68;
      }
      v82 = WfpReportSysErrorAsNtStatus(v50, "HeapAlloc", 3221225495LL);
      v52 = v82;
      if ( v82 )
      {
        v83 = "WfpMemAlloc";
        goto LABEL_142;
      }
    }
LABEL_68:
    if ( !v52 )
    {
      IkePushTraceAlloc(v3, v51);
      *v51 = v47;
      v62 = 2LL * *v3;
      *(_QWORD *)&v3[2 * v62 + 2] = v51;
      *(_QWORD *)&v3[2 * v62 + 4] = 8;
      ++*v3;
    }
    goto LABEL_70;
  }
  v52 = WfpReportSysErrorAsWinError(v46, "IkeTraceUInt64", 122, 1);
LABEL_70:
  IkeReturnError(v52, "IkeTraceUInt64");
  v53 = 0;
  v54 = EtwEventWrite(WfpEventTraceHandle, WFP_MM_TERMINATION_SUCCESS_V1, *v3, v3 + 2);
  if ( v54 )
    v53 = WfpReportSysErrorAsWinError(v55, "EtwEventWrite", v54, 1);
  v2 = IkeReturnError(v53, "IkeWriteEvent");
  EtwEventActivityIdControl(2, &v90);
LABEL_73:
  IkeFreeTraceParams(v3);
  return IkeReturnError(v2, "IkeTraceMMTerminationSuccess");
}

```

## disassembly

```asm
0x18000ee10  push    rbp
0x18000ee12  push    rbx
0x18000ee13  push    rsi
0x18000ee14  push    rdi
0x18000ee15  push    r12
0x18000ee17  push    r13
0x18000ee19  push    r14
0x18000ee1b  push    r15
0x18000ee1d  lea     rbp, [rsp-1Fh]
0x18000ee22  sub     rsp, 98h
0x18000ee29  mov     rax, cs:__security_cookie
0x18000ee30  xor     rax, rsp
0x18000ee33  mov     [rbp+57h+var_50], rax
0x18000ee37  xorps   xmm0, xmm0
0x18000ee3a  mov     [rbp+57h+var_A0], rcx
0x18000ee3e  movups  [rbp+57h+var_60], xmm0
0x18000ee42  mov     r14, rcx
0x18000ee45  xor     edi, edi
0x18000ee47  xor     ebx, ebx
0x18000ee49  call    WfpIsTraceEnabled
0x18000ee4e  test    al, al
0x18000ee50  jz      loc_18000F321
0x18000ee56  mov     rcx, cs:WfpEventTraceHandle
0x18000ee5d  lea     rdx, WFP_MM_TERMINATION_SUCCESS_V1
0x18000ee64  call    cs:__imp_EtwEventEnabled
0x18000ee6a  test    al, al
0x18000ee6c  jz      loc_18000F321
0x18000ee72  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000ee78  test    al, 10h
0x18000ee7a  jnz     loc_18000F55D
0x18000ee80  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000ee85  mov     rcx, cs:gWfpHeap; hHeap
0x18000ee8c  mov     r15d, 8
0x18000ee92  mov     edx, r15d; dwFlags
0x18000ee95  mov     r8d, 3D0h; dwBytes
0x18000ee9b  test    eax, eax
0x18000ee9d  jnz     loc_18000F3B0
0x18000eea3  call    cs:__imp_HeapAlloc
0x18000eea9  mov     r12d, 0C0000017h
0x18000eeaf  lea     r13, aHeapalloc; "HeapAlloc"
0x18000eeb6  mov     rbx, rax
0x18000eeb9  test    rax, rax
0x18000eebc  jz      loc_18000F599
0x18000eec2  cmp     cs:gWfpTrackHeapBytes, edi
0x18000eec8  jnz     loc_18000F5B2
0x18000eece  lea     rdx, aIkeallocatetra; "IkeAllocateTraceParams"
0x18000eed5  mov     rcx, rdi
0x18000eed8  call    IkeReturnError
0x18000eedd  mov     rdi, rax
0x18000eee0  test    rax, rax
0x18000eee3  jnz     loc_18000F321
0x18000eee9  lea     rdx, [rbp+57h+var_60]
0x18000eeed  lea     ecx, [rax+1]
0x18000eef0  call    cs:__imp_EtwEventActivityIdControl
0x18000eef6  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18000eefc  mov     edi, 2
0x18000ef01  test    eax, eax
0x18000ef03  jnz     loc_18000F5D0
0x18000ef09  xorps   xmm1, xmm1
0x18000ef0c  mov     [rbp+57h+var_98], 0
0x18000ef14  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x18000ef18  lea     r11, [r14+178h]
0x18000ef1f  xorps   xmm0, xmm0
0x18000ef22  lea     r8, [rbp+57h+var_B0]
0x18000ef26  mov     rcx, r11
0x18000ef29  lea     rdx, [rbp+57h+var_98]
0x18000ef2d  movups  xmmword ptr [rbp+57h+var_80+0Ch], xmm1
0x18000ef31  movups  [rbp+57h+var_90], xmm0
0x18000ef35  call    IkeAddrGetAddrBytes
0x18000ef3a  mov     rcx, r11
0x18000ef3d  call    IkeAddrGetIPVersion
0x18000ef42  mov     ecx, 1Ch
0x18000ef47  mov     [rbp+57h+var_B0], ecx
0x18000ef4a  lea     edx, [rcx-5]
0x18000ef4d  test    eax, eax
0x18000ef4f  jnz     loc_18000F50F
0x18000ef55  mov     rax, [rbp+57h+var_98]
0x18000ef59  lea     r14d, [rcx-0Ch]
0x18000ef5d  movups  [rbp+57h+var_90], xmm0
0x18000ef61  lea     rdx, [rbp+57h+var_90]
0x18000ef65  mov     word ptr [rbp+57h+var_90], di
0x18000ef69  mov     [rbp+57h+var_A8], rdx
0x18000ef6d  mov     ecx, [rax]
0x18000ef6f  mov     dword ptr [rbp+57h+var_90+4], ecx
0x18000ef72  mov     esi, 4
0x18000ef77  add     [rbx+4], esi
0x18000ef7a  cmp     dword ptr [rbx+4], 2000h
0x18000ef81  jnb     loc_18000F5F1
0x18000ef87  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000ef8d  test    al, 10h
0x18000ef8f  jnz     loc_18000F60F
0x18000ef95  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000ef9a  mov     rcx, cs:gWfpHeap; hHeap
0x18000efa1  xor     edx, edx; dwFlags
0x18000efa3  mov     r8, rsi; dwBytes
0x18000efa6  test    eax, eax
0x18000efa8  jnz     loc_18000F358
0x18000efae  call    cs:__imp_HeapAlloc
0x18000efb4  mov     rsi, rax
0x18000efb7  test    rax, rax
0x18000efba  jz      loc_18000F64B
0x18000efc0  xor     edi, edi
0x18000efc2  cmp     cs:gWfpTrackHeapBytes, edi
0x18000efc8  jnz     loc_18000F664
0x18000efce  test    rdi, rdi
0x18000efd1  jz      loc_18000F682
0x18000efd7  mov     esi, 4
0x18000efdc  lea     rdx, aIketraceuint32; "IkeTraceUInt32"
0x18000efe3  mov     rcx, rdi
0x18000efe6  call    IkeReturnError
0x18000efeb  mov     rdx, [rbp+57h+var_A8]
0x18000efef  mov     r9d, 1
0x18000eff5  mov     r8d, r14d
0x18000eff8  mov     rcx, rbx
0x18000effb  call    IkeTraceBytes
0x18000f000  mov     r11, [rbp+57h+var_A0]
0x18000f004  lea     r8, [rbp+57h+var_98]
0x18000f008  xorps   xmm1, xmm1
0x18000f00b  mov     [rbp+57h+var_A8], 0
0x18000f013  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x18000f017  lea     rdx, [rbp+57h+var_A8]
0x18000f01b  xorps   xmm0, xmm0
0x18000f01e  lea     rcx, [r11+1B4h]
0x18000f025  movups  [rbp+57h+var_90], xmm0
0x18000f029  movups  xmmword ptr [rbp+57h+var_80+0Ch], xmm1
0x18000f02d  call    IkeAddrGetAddrBytes
0x18000f032  lea     rcx, [r11+1B4h]
0x18000f039  call    IkeAddrGetIPVersion
0x18000f03e  test    eax, eax
0x18000f040  jnz     loc_18000F537
0x18000f046  movups  [rbp+57h+var_90], xmm0
0x18000f04a  mov     eax, 2
0x18000f04f  mov     [rbp+57h+var_B0], 10h
0x18000f056  mov     word ptr [rbp+57h+var_90], ax
0x18000f05a  lea     r14, [rbp+57h+var_90]
0x18000f05e  mov     rax, [rbp+57h+var_A8]
0x18000f062  mov     ecx, [rax]
0x18000f064  mov     dword ptr [rbp+57h+var_90+4], ecx
0x18000f067  add     [rbx+4], esi
0x18000f06a  cmp     dword ptr [rbx+4], 2000h
0x18000f071  jnb     loc_18000F6AB
0x18000f077  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000f07d  test    al, 10h
0x18000f07f  jnz     loc_18000F6C9
0x18000f085  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000f08a  mov     rcx, cs:gWfpHeap; hHeap
0x18000f091  xor     edx, edx; dwFlags
0x18000f093  mov     r8, rsi; dwBytes
0x18000f096  test    eax, eax
0x18000f098  jnz     loc_18000F384
0x18000f09e  call    cs:__imp_HeapAlloc
0x18000f0a4  mov     rsi, rax
0x18000f0a7  test    rax, rax
0x18000f0aa  jz      loc_18000F705
0x18000f0b0  xor     edi, edi
0x18000f0b2  cmp     cs:gWfpTrackHeapBytes, edi
0x18000f0b8  jnz     loc_18000F71E
0x18000f0be  test    rdi, rdi
0x18000f0c1  jz      loc_18000F73C
0x18000f0c7  mov     esi, 4
0x18000f0cc  lea     rdx, aIketraceuint32; "IkeTraceUInt32"
0x18000f0d3  mov     rcx, rdi
0x18000f0d6  call    IkeReturnError
0x18000f0db  mov     r8d, [rbp+57h+var_B0]
0x18000f0df  mov     r9d, 1
0x18000f0e5  mov     rdx, r14
0x18000f0e8  mov     rcx, rbx
0x18000f0eb  call    IkeTraceBytes
0x18000f0f0  mov     rax, [rbp+57h+var_A0]
0x18000f0f4  mov     r14d, [rax+248h]
0x18000f0fb  add     [rbx+4], esi
0x18000f0fe  cmp     dword ptr [rbx+4], 2000h
0x18000f105  jnb     loc_18000F767
0x18000f10b  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000f111  test    al, 10h
0x18000f113  jnz     loc_18000F785
0x18000f119  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000f11e  mov     rcx, cs:gWfpHeap; hHeap
0x18000f125  xor     edx, edx; dwFlags
0x18000f127  mov     r8, rsi; dwBytes
0x18000f12a  test    eax, eax
0x18000f12c  jnz     loc_18000F4E3
0x18000f132  call    cs:__imp_HeapAlloc
0x18000f138  mov     rsi, rax
0x18000f13b  test    rax, rax
0x18000f13e  jz      loc_18000F7C1
0x18000f144  xor     edi, edi
0x18000f146  cmp     cs:gWfpTrackHeapBytes, edi
0x18000f14c  jnz     loc_18000F7DA
0x18000f152  test    rdi, rdi
0x18000f155  jz      loc_18000F7F8
0x18000f15b  lea     rdx, aIketraceuint32; "IkeTraceUInt32"
0x18000f162  mov     rcx, rdi
0x18000f165  call    IkeReturnError
0x18000f16a  mov     rax, [rbp+57h+var_A0]
0x18000f16e  mov     r14, [rax+3E0h]
0x18000f175  add     [rbx+4], r15d
0x18000f179  cmp     dword ptr [rbx+4], 2000h
0x18000f180  jnb     loc_18000F820
0x18000f186  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000f18c  test    al, 10h
0x18000f18e  jnz     loc_18000F83E
0x18000f194  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000f199  mov     rcx, cs:gWfpHeap; hHeap
0x18000f1a0  xor     edx, edx; dwFlags
0x18000f1a2  mov     r8, r15; dwBytes
0x18000f1a5  test    eax, eax
0x18000f1a7  jnz     loc_18000F45F
0x18000f1ad  call    cs:__imp_HeapAlloc
0x18000f1b3  mov     rsi, rax
0x18000f1b6  test    rax, rax
0x18000f1b9  jz      loc_18000F87A
0x18000f1bf  xor     edi, edi
0x18000f1c1  cmp     cs:gWfpTrackHeapBytes, edi
0x18000f1c7  jnz     loc_18000F893
0x18000f1cd  test    rdi, rdi
0x18000f1d0  jz      loc_18000F3E7
0x18000f1d6  lea     rdx, aIketraceuint64; "IkeTraceUInt64"
0x18000f1dd  mov     rcx, rdi
0x18000f1e0  call    IkeReturnError
0x18000f1e5  mov     rax, [rbp+57h+var_A0]
0x18000f1e9  mov     r14, [rax+2A8h]
0x18000f1f0  add     [rbx+4], r15d
0x18000f1f4  cmp     dword ptr [rbx+4], 2000h
0x18000f1fb  jnb     loc_18000F8B1
0x18000f201  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000f207  test    al, 10h
0x18000f209  jnz     loc_18000F8CF
0x18000f20f  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000f214  mov     rcx, cs:gWfpHeap; hHeap
0x18000f21b  xor     edx, edx; dwFlags
0x18000f21d  mov     r8, r15; dwBytes
0x18000f220  test    eax, eax
0x18000f222  jnz     loc_18000F48B
0x18000f228  call    cs:__imp_HeapAlloc
0x18000f22e  mov     rsi, rax
0x18000f231  test    rax, rax
0x18000f234  jz      loc_18000F90B
0x18000f23a  xor     edi, edi
0x18000f23c  cmp     cs:gWfpTrackHeapBytes, edi
0x18000f242  jnz     loc_18000F924
0x18000f248  test    rdi, rdi
0x18000f24b  jz      loc_18000F40F
0x18000f251  lea     rdx, aIketraceuint64; "IkeTraceUInt64"
0x18000f258  mov     rcx, rdi
0x18000f25b  call    IkeReturnError
0x18000f260  mov     rax, [rbp+57h+var_A0]
0x18000f264  mov     r14, [rax+2B0h]
0x18000f26b  add     [rbx+4], r15d
0x18000f26f  cmp     dword ptr [rbx+4], 2000h
0x18000f276  jnb     loc_18000F942
0x18000f27c  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000f282  test    al, 10h
0x18000f284  jnz     loc_18000F960
0x18000f28a  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000f28f  mov     rcx, cs:gWfpHeap; hHeap
0x18000f296  xor     edx, edx; dwFlags
0x18000f298  mov     r8, r15; dwBytes
0x18000f29b  test    eax, eax
0x18000f29d  jnz     loc_18000F4B7
0x18000f2a3  call    cs:__imp_HeapAlloc
0x18000f2a9  mov     rsi, rax
0x18000f2ac  test    rax, rax
0x18000f2af  jz      loc_18000F99C
0x18000f2b5  xor     edi, edi
0x18000f2b7  cmp     cs:gWfpTrackHeapBytes, edi
0x18000f2bd  jnz     loc_18000F9B5
0x18000f2c3  test    rdi, rdi
0x18000f2c6  jz      loc_18000F437
0x18000f2cc  lea     rdx, aIketraceuint64; "IkeTraceUInt64"
0x18000f2d3  mov     rcx, rdi
0x18000f2d6  call    IkeReturnError
0x18000f2db  mov     r8d, [rbx]
0x18000f2de  lea     r9, [rbx+8]
0x18000f2e2  mov     rcx, cs:WfpEventTraceHandle
0x18000f2e9  lea     rdx, WFP_MM_TERMINATION_SUCCESS_V1
0x18000f2f0  xor     edi, edi
0x18000f2f2  call    cs:__imp_EtwEventWrite
0x18000f2f8  test    eax, eax
0x18000f2fa  jnz     loc_18000F9D3
0x18000f300  lea     rdx, aIkewriteevent; "IkeWriteEvent"
0x18000f307  mov     rcx, rdi
0x18000f30a  call    IkeReturnError
0x18000f30f  lea     rdx, [rbp+57h+var_60]
0x18000f313  mov     ecx, 2
0x18000f318  mov     rdi, rax
0x18000f31b  call    cs:__imp_EtwEventActivityIdControl
0x18000f321  mov     rcx, rbx
0x18000f324  call    IkeFreeTraceParams
0x18000f329  lea     rdx, aIketracemmterm; "IkeTraceMMTerminationSuccess"
0x18000f330  mov     rcx, rdi
0x18000f333  call    IkeReturnError
0x18000f338  mov     rcx, [rbp+57h+var_50]
0x18000f33c  xor     rcx, rsp; StackCookie
0x18000f33f  call    __security_check_cookie
0x18000f344  add     rsp, 98h
0x18000f34b  pop     r15
0x18000f34d  pop     r14
0x18000f34f  pop     r13
0x18000f351  pop     r12
  ... truncated ...
```
