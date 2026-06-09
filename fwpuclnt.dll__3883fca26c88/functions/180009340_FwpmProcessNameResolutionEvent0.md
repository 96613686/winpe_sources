# FwpmProcessNameResolutionEvent0

- ea: `0x180009340`
- end: `0x180009bb4`
- name: `FwpmProcessNameResolutionEvent0`
- size: `2164`
- prototype: `__int64 __fastcall(u_long netlong)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180009230`

## callees

- `0x180002eb0`
- `0x1800034e0`
- `0x180003704`
- `0x1800072e0`
- `0x180007550`
- `0x180007e38`
- `0x180009340`
- `0x18000aee0`
- `0x18000dd70`
- `0x18000e898`
- `0x180012bd0`
- `0x18001346a`
- `0x180018e5c`
- `0x180038c38`
- `0x180038dd8`
- `0x180038ec4`
- `0x18003a298`
- `0x18004703c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b0a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800096c9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800099f7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009ae9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800096c9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800099f7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009ae9`
- `RPCRT4!NdrClientCall3` at `0x18000953e`
- `RPCRT4!NdrClientCall3` at `0x1800098ec`
- `RPCRT4!NdrClientCall3` at `0x18000953e`
- `RPCRT4!NdrClientCall3` at `0x1800098ec`
- `WS2_32!__imp_ntohl` at `0x18000985e`
- `WS2_32!__imp_ntohl` at `0x18000985e`

## string_xrefs

- `0x1800094e0`: `FwpmEngineOpen0`
- `0x1800094f2`: `FwpmEngineOpen0`
- `0x180009504`: `FwpmEngineOpen0`
- `0x180009440`: `Name Resolution Cache Session`
- `0x180009721`: `FwpIsNameCacheEnabledForProcess`

## pseudocode

```c
__int64 __fastcall FwpmProcessNameResolutionEvent0(u_long netlong, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  void *v8; // rsi
  void *v9; // r15
  __int64 IsProcessInAppContainer; // rbx
  _QWORD *v11; // r12
  int v12; // r14d
  __int64 v13; // rax
  __int64 v14; // r8
  const char *v15; // rdx
  const char *v16; // rdx
  unsigned int Pointer; // eax
  __int64 v18; // rax
  int v19; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  void *v21; // r8
  BOOL v22; // eax
  void *v23; // r8
  __int64 v24; // rdx
  void *v25; // rcx
  __int64 v26; // r8
  int v27; // r14d
  __int64 ExpandedPeerName; // rax
  u_long v29; // eax
  unsigned int v30; // eax
  CLIENT_CALL_RETURN v31; // rcx
  int v32; // eax
  BOOL v33; // eax
  int v34; // eax
  BOOL v35; // eax
  unsigned int v36; // edx
  int v37; // eax
  __int64 v39; // [rsp+30h] [rbp-D8h]
  __int64 v40; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD *v41; // [rsp+60h] [rbp-A8h] BYREF
  void *v42; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-98h]
  HANDLE engineHandle; // [rsp+78h] [rbp-90h] BYREF
  __int64 v45; // [rsp+80h] [rbp-88h]
  __int64 v46; // [rsp+88h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-78h] BYREF
  void *p[2]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v49; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-50h]
  __int128 v51; // [rsp+C8h] [rbp-40h]
  __int128 v52; // [rsp+D8h] [rbp-30h]
  __int64 v53; // [rsp+E8h] [rbp-20h]
  _BYTE v54[112]; // [rsp+F8h] [rbp-10h] BYREF
  int v55; // [rsp+168h] [rbp+60h]
  char *v56; // [rsp+170h] [rbp+68h]
  int TokenInformation; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v58; // [rsp+1D0h] [rbp+C8h] BYREF
  int v59; // [rsp+1D8h] [rbp+D0h]
  __int128 v60; // [rsp+1E0h] [rbp+D8h] BYREF
  __int128 v61; // [rsp+1F0h] [rbp+E8h] BYREF
  _BYTE v62[16]; // [rsp+200h] [rbp+F8h] BYREF
  const char *v63; // [rsp+210h] [rbp+108h]
  __int64 v64; // [rsp+218h] [rbp+110h]
  __int64 *v65; // [rsp+220h] [rbp+118h]
  __int64 v66; // [rsp+228h] [rbp+120h]
  char v67; // [rsp+238h] [rbp+130h] BYREF

  v46 = a3;
  v43 = a2;
  v45 = a4;
  engineHandle = 0;
  memset_0(v54, 0, 0xC8u);
  v40 = 0;
  p[0] = 0;
  v8 = 0;
  v59 = 0;
  v9 = 0;
  v58 = 0;
  IsProcessInAppContainer = 0;
  v61 = 0;
  v42 = 0;
  v11 = 0;
  v60 = 0;
  TokenInformation = 0;
  v41 = 0;
  v49 = 0;
  v53 = 0;
  v50 = 0;
  lpMem = 0;
  v51 = 0;
  v52 = 0;
  if ( (_DWORD)qword_18007C418 )
  {
    v12 = HIDWORD(qword_18007C418);
    goto LABEL_42;
  }
  v12 = 0;
  IsProcessInAppContainer = WfpIsProcessInAppContainer(&TokenInformation);
  if ( !IsProcessInAppContainer )
  {
    if ( TokenInformation )
    {
      qword_18007C418 = 1;
      goto LABEL_42;
    }
    *(_QWORD *)&v51 = 0x271010000000LL;
    *(_QWORD *)&v50 = L"Name Resolution Cache Session";
    FwppCompleteInit();
    v13 = FwppSessionCreate(0, 0xFFFFFFFFLL, 0, (__int64)&v49, &v41);
    v11 = v41;
    if ( !v13 )
      goto LABEL_14;
    v7 = (unsigned __int16)v13;
    v6 = v13 & 0x1FFF0000;
    if ( (_DWORD)v6 != 458752 )
      v7 = (unsigned int)v13;
    switch ( (_DWORD)v7 )
    {
      case 0x6BF:
      case 6:
        v7 = 2150760464LL;
        break;
      case 0x6C5:
        v7 = 2150760477LL;
        v16 = "FwpmEngineOpen0";
        goto LABEL_36;
      case 0x6EF:
      case 0x6F4:
        v7 = 2150760476LL;
        v16 = "FwpmEngineOpen0";
        goto LABEL_36;
      case 0:
LABEL_14:
        lpMem = 0;
        if ( v41 )
        {
          Pointer = (unsigned int)NdrClientCall3(
                                    (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                    4u,
                                    0,
                                    *v41,
                                    v41[1],
                                    2,
                                    &lpMem).Pointer;
          if ( !Pointer )
            goto LABEL_31;
          v14 = Pointer;
          v15 = "FwppProxyEngineGetOption";
        }
        else
        {
          v14 = 2150760476LL;
          v15 = "FwpmEngineGetOption0";
        }
        v18 = WfpReportSysErrorAsWinError(v6, v15, v14);
        v6 = v18;
        if ( v18 )
        {
          v7 = (unsigned __int16)v18;
          if ( (v18 & 0x1FFF0000) != 0x70000 )
            v7 = (unsigned int)v18;
          switch ( (_DWORD)v7 )
          {
            case 0x6BF:
            case 6:
              v7 = 2150760464LL;
              break;
            case 0x6C5:
              v7 = 2150760477LL;
              break;
            case 0x6EF:
            case 0x6F4:
              v7 = 2150760476LL;
              break;
            case 0:
              goto LABEL_31;
          }
          v16 = "FwpmEngineGetOption0";
LABEL_36:
          IsProcessInAppContainer = WfpReportSysErrorAsWinError(v6, v16, v7);
          if ( !IsProcessInAppContainer )
            goto LABEL_42;
          goto LABEL_37;
        }
LABEL_31:
        v12 = *((_DWORD *)lpMem + 2);
        HIDWORD(qword_18007C418) = v12;
        LODWORD(qword_18007C418) = 1;
        goto LABEL_42;
    }
    v16 = "FwpmEngineOpen0";
    goto LABEL_36;
  }
LABEL_37:
  v19 = (unsigned __int16)IsProcessInAppContainer;
  v6 = IsProcessInAppContainer & 0x1FFF0000;
  if ( (_DWORD)v6 != 458752 )
    v19 = IsProcessInAppContainer;
  if ( v19 == 1753 )
    qword_18007C418 = 1;
LABEL_42:
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v6, v5, v7);
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( gWfpTrackHeapAllocs )
    {
      v21 = lpMem;
      if ( !lpMem )
      {
LABEL_55:
        v22 = HeapFree(gWfpHeap, 0, v21);
        if ( !gHeapFreeFailedFired && !v22 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          gHeapFreeFailedFired = 1;
        }
        goto LABEL_62;
      }
      if ( _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
      {
        if ( !gMisalignedHeapTelemFired )
        {
          if ( gWfpNumHeapAllocs <= 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          gMisalignedHeapTelemFired = 1;
        }
        _InterlockedIncrement(&gWfpNumHeapAllocs);
        goto LABEL_62;
      }
    }
    v21 = lpMem;
    goto LABEL_55;
  }
  v23 = lpMem;
  if ( gWfpTrackHeapBytes && lpMem )
  {
    _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, lpMem));
    v23 = lpMem;
  }
  HeapFree(gWfpHeap, 0, v23);
LABEL_62:
  v41 = v11;
  lpMem = (LPVOID)0xBADBADFABADBADFALL;
  FwppSessionDestroy(&v41);
  if ( IsProcessInAppContainer )
  {
    WfpReportError(IsProcessInAppContainer, "FwpIsNameCacheEnabledForProcess");
  }
  else if ( v12 )
  {
    v27 = v43;
    if ( netlong || v43 )
    {
      ExpandedPeerName = FwpGetExpandedPeerName(netlong, v43, v45, &v42);
      v9 = v42;
      IsProcessInAppContainer = ExpandedPeerName;
      if ( !ExpandedPeerName )
      {
        IsProcessInAppContainer = FwpNameCacheGetEngineHandle(&engineHandle, (__int64)v42, (LPVOID *)&v40);
        if ( IsProcessInAppContainer )
        {
          v8 = (void *)v40;
        }
        else
        {
          v55 = 4;
          v56 = &v67;
          v29 = ntohl(netlong);
          v8 = (void *)v40;
          IsProcessInAppContainer = FwppConstructNameResolutionFilter(
                                      v29,
                                      v27,
                                      v46,
                                      (_DWORD)v9,
                                      (__int64)&v61,
                                      (__int64)&v60,
                                      (__int64)&v58,
                                      v40,
                                      (__int64)v54);
          if ( !IsProcessInAppContainer )
          {
            v30 = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                  0xB7u,
                                  0,
                                  *(_QWORD *)engineHandle,
                                  *((_QWORD *)engineHandle + 1),
                                  v54,
                                  p).Pointer;
            if ( p[0] )
            {
              v31.Simple = *((unsigned int *)p[0] + 2);
              dword_18007C404 = *((_DWORD *)p[0] + 2);
            }
            if ( v30 )
              IsProcessInAppContainer = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))WfpReportSysErrorAsWinError)(
                                          (CLIENT_CALL_RETURN)v31.Simple,
                                          "FwppProxyBfeProcessNameResolutionEvent",
                                          v30);
            else
              IsProcessInAppContainer = FwpProcessNameResolutionResponse(p[0], v8);
          }
        }
      }
    }
    else
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(v39) = 87;
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v26, 0, (__int64)"FwpmProcessNameResolutionEvent0", v39);
      }
      if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
      {
        LODWORD(v40) = 87;
        v65 = &v40;
        v63 = "FwpmProcessNameResolutionEvent0";
        v64 = 32;
        v66 = 4;
        McGenEventWrite_EtwEventWriteTransfer((__int64)v25, (__int64)WFP_USERMODE_ERROR, v26, 3, (__int64)v62);
      }
      IsProcessInAppContainer = -2147024809;
    }
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v32 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v32 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v25, v24, v26);
  if ( v32 )
  {
    if ( gWfpTrackHeapAllocs && v8 && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
    {
      if ( !gMisalignedHeapTelemFired )
      {
        if ( gWfpNumHeapAllocs <= 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        gMisalignedHeapTelemFired = 1;
      }
      _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v33 = HeapFree(gWfpHeap, 0, v8);
      if ( !gHeapFreeFailedFired && !v33 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        gHeapFreeFailedFired = 1;
      }
    }
  }
  else
  {
    if ( gWfpTrackHeapBytes && v8 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v8));
    HeapFree(gWfpHeap, 0, v8);
  }
  if ( p[0] )
    FwpmFreeMemory0(p);
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v34 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v34 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v25, v24, v26);
  if ( v34 )
  {
    if ( gWfpTrackHeapAllocs && v9 && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
    {
      if ( !gMisalignedHeapTelemFired )
      {
        if ( gWfpNumHeapAllocs <= 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        gMisalignedHeapTelemFired = 1;
      }
      _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v35 = HeapFree(gWfpHeap, 0, v9);
      if ( !gHeapFreeFailedFired && !v35 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        gHeapFreeFailedFired = 1;
      }
    }
  }
  else
  {
    if ( gWfpTrackHeapBytes && v9 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v9));
    HeapFree(gWfpHeap, 0, v9);
  }
  if ( !IsProcessInAppContainer )
    return 0;
  v36 = (unsigned __int16)IsProcessInAppContainer;
  if ( (IsProcessInAppContainer & 0x1FFF0000) != 0x70000 )
    v36 = IsProcessInAppContainer;
  if ( v36 == 1753 )
  {
    v37 = 0;
    dword_18007C404 = 0;
  }
  else
  {
    v37 = dword_18007C404;
  }
  if ( !v37 || v36 == 9003 )
    return 0;
  switch ( v36 )
  {
    case 6u:
    case 0x6BFu:
      return 2150760464LL;
    case 0x6C5u:
      return 2150760477LL;
    case 0x6EFu:
    case 0x6F4u:
      return 2150760476LL;
  }
  return v36;
}

```

## disassembly

```asm
0x180009340  mov     r11, rsp
0x180009343  push    rbp
0x180009344  push    rbx
0x180009345  lea     rbp, [r11-228h]
0x18000934c  sub     rsp, 318h
0x180009353  mov     rax, cs:__security_cookie
0x18000935a  xor     rax, rsp
0x18000935d  mov     [rbp+220h+var_50], rax
0x180009364  mov     [r11-18h], rsi
0x180009368  mov     [r11-20h], rdi
0x18000936c  xor     edi, edi
0x18000936e  mov     [r11-28h], r12
0x180009372  mov     [r11-30h], r13
0x180009376  mov     r13d, ecx
0x180009379  mov     [rbp+220h+var_2A0], r8
0x18000937d  lea     rcx, [rbp+220h+var_230]; void *
0x180009381  mov     [rsp+320h+var_2B8], rdx
0x180009386  mov     r8d, 0C8h; Size
0x18000938c  mov     [r11-38h], r14
0x180009390  xor     edx, edx; Val
0x180009392  mov     [r11-40h], r15
0x180009396  mov     [rsp+320h+var_2A8], r9
0x18000939b  mov     [rsp+320h+engineHandle], rdi
0x1800093a0  call    memset_0
0x1800093a5  xorps   xmm0, xmm0
0x1800093a8  mov     [rsp+320h+var_2D0], rdi
0x1800093ad  xor     eax, eax
0x1800093af  mov     [rbp+220h+p], rdi
0x1800093b3  cmp     dword ptr cs:qword_18007C418, eax
0x1800093b9  mov     esi, edi
0x1800093bb  mov     [rbp+220h+var_154], rax
0x1800093c2  mov     r15d, edi
0x1800093c5  mov     [rbp+0C8h], rax
0x1800093cc  mov     ebx, edi
0x1800093ce  movups  [rbp+220h+var_138], xmm0
0x1800093d5  mov     [rsp+320h+var_2C0], rdi
0x1800093da  mov     r12d, edi
0x1800093dd  movups  [rbp+220h+var_148], xmm0
0x1800093e4  mov     [rbp+220h+TokenInformation], edi
0x1800093ea  mov     [rsp+320h+var_2C8], rdi
0x1800093ef  movups  [rbp+220h+var_280], xmm0
0x1800093f3  mov     [rbp+220h+var_240], rax
0x1800093f7  movups  [rbp+220h+var_270], xmm0
0x1800093fb  mov     [rbp+220h+lpMem], rdi
0x1800093ff  movups  [rbp+220h+var_260], xmm0
0x180009403  movups  [rbp+220h+var_250], xmm0
0x180009407  jnz     loc_18000960D
0x18000940d  lea     rcx, [rbp+220h+TokenInformation]; TokenInformation
0x180009414  mov     r14d, edi
0x180009417  call    WfpIsProcessInAppContainer
0x18000941c  mov     rbx, rax
0x18000941f  test    rax, rax
0x180009422  jnz     loc_1800095E5
0x180009428  cmp     [rbp+220h+TokenInformation], esi
0x18000942e  jz      short loc_180009440
0x180009430  mov     cs:qword_18007C418, 1
0x18000943b  jmp     loc_180009614
0x180009440  lea     rax, aNameResolution; "Name Resolution Cache Session"
0x180009447  mov     dword ptr [rbp+220h+var_260], 10000000h
0x18000944e  mov     qword ptr [rbp+220h+var_270], rax
0x180009452  mov     dword ptr [rbp+220h+var_260+4], 2710h
0x180009459  call    FwppCompleteInit
0x18000945e  lea     rax, [rsp+320h+var_2C8]
0x180009463  xor     r8d, r8d
0x180009466  lea     r9, [rbp+220h+var_280]
0x18000946a  mov     [rsp+320h+var_300], rax
0x18000946f  mov     edx, 0FFFFFFFFh
0x180009474  xor     ecx, ecx
0x180009476  call    FwppSessionCreate
0x18000947b  mov     r12, [rsp+320h+var_2C8]
0x180009480  test    rax, rax
0x180009483  jz      short loc_1800094C2
0x180009485  mov     ecx, eax
0x180009487  movzx   r8d, ax
0x18000948b  and     ecx, 1FFF0000h
0x180009491  cmp     ecx, 70000h
0x180009497  cmovnz  r8d, eax
0x18000949b  cmp     r8d, 6BFh
0x1800094a2  jz      short loc_1800094FE
0x1800094a4  mov     eax, r8d
0x1800094a7  sub     eax, 6
0x1800094aa  jz      short loc_1800094FE
0x1800094ac  sub     eax, 6BFh
0x1800094b1  jz      short loc_1800094EC
0x1800094b3  sub     eax, 2Ah ; '*'
0x1800094b6  jz      short loc_1800094DA
0x1800094b8  cmp     eax, 5
0x1800094bb  jz      short loc_1800094DA
0x1800094bd  test    r8d, r8d
0x1800094c0  jnz     short loc_180009504
0x1800094c2  mov     [rbp+220h+lpMem], rdi
0x1800094c6  test    r12, r12
0x1800094c9  jnz     short loc_180009510
0x1800094cb  mov     r8d, 8032001Ch
0x1800094d1  lea     rdx, aFwpmenginegeto_0; "FwpmEngineGetOption0"
0x1800094d8  jmp     short loc_180009558
0x1800094da  mov     r8d, 8032001Ch
0x1800094e0  lea     rdx, aFwpmengineopen_0; "FwpmEngineOpen0"
0x1800094e7  jmp     loc_1800095D8
0x1800094ec  mov     r8d, 8032001Dh
0x1800094f2  lea     rdx, aFwpmengineopen_0; "FwpmEngineOpen0"
0x1800094f9  jmp     loc_1800095D8
0x1800094fe  mov     r8d, 80320010h
0x180009504  lea     rdx, aFwpmengineopen_0; "FwpmEngineOpen0"
0x18000950b  jmp     loc_1800095D8
0x180009510  mov     r9, [r12]
0x180009514  lea     rax, [rbp+220h+lpMem]
0x180009518  mov     [rsp+320h+var_2F0], rax
0x18000951d  lea     rcx, pProxyInfo; pProxyInfo
0x180009524  mov     rax, [r12+8]
0x180009529  xor     r8d, r8d; pReturnValue
0x18000952c  mov     dword ptr [rsp+320h+var_2F8], 2
0x180009534  mov     edx, 4; nProcNum
0x180009539  mov     [rsp+320h+var_300], rax
0x18000953e  call    cs:__imp_NdrClientCall3
0x180009545  nop     dword ptr [rax+rax+00h]
0x18000954a  test    eax, eax
0x18000954c  jz      short loc_1800095A0
0x18000954e  mov     r8d, eax
0x180009551  lea     rdx, aFwppproxyengin_0; "FwppProxyEngineGetOption"
0x180009558  call    WfpReportSysErrorAsWinError
0x18000955d  mov     rcx, rax
0x180009560  test    rax, rax
0x180009563  jz      short loc_1800095A0
0x180009565  mov     eax, ecx
0x180009567  movzx   r8d, cx
0x18000956b  and     eax, 1FFF0000h
0x180009570  cmp     eax, 70000h
0x180009575  cmovnz  r8d, ecx
0x180009579  cmp     r8d, 6BFh
0x180009580  jz      short loc_1800095CB
0x180009582  mov     eax, r8d
0x180009585  sub     eax, 6
0x180009588  jz      short loc_1800095CB
0x18000958a  sub     eax, 6BFh
0x18000958f  jz      short loc_1800095C3
0x180009591  sub     eax, 2Ah ; '*'
0x180009594  jz      short loc_1800095BB
0x180009596  cmp     eax, 5
0x180009599  jz      short loc_1800095BB
0x18000959b  test    r8d, r8d
0x18000959e  jnz     short loc_1800095D1
0x1800095a0  mov     rax, [rbp+220h+lpMem]
0x1800095a4  mov     r14d, [rax+8]
0x1800095a8  mov     dword ptr cs:qword_18007C418+4, r14d
0x1800095af  mov     dword ptr cs:qword_18007C418, 1
0x1800095b9  jmp     short loc_180009614
0x1800095bb  mov     r8d, 8032001Ch
0x1800095c1  jmp     short loc_1800095D1
0x1800095c3  mov     r8d, 8032001Dh
0x1800095c9  jmp     short loc_1800095D1
0x1800095cb  mov     r8d, 80320010h
0x1800095d1  lea     rdx, aFwpmenginegeto_0; "FwpmEngineGetOption0"
0x1800095d8  call    WfpReportSysErrorAsWinError
0x1800095dd  mov     rbx, rax
0x1800095e0  test    rax, rax
0x1800095e3  jz      short loc_180009614
0x1800095e5  mov     ecx, ebx
0x1800095e7  movzx   eax, bx
0x1800095ea  and     ecx, 1FFF0000h
0x1800095f0  cmp     ecx, 70000h
0x1800095f6  cmovnz  eax, ebx
0x1800095f9  cmp     eax, 6D9h
0x1800095fe  jnz     short loc_180009614
0x180009600  mov     cs:qword_18007C418, 1
0x18000960b  jmp     short loc_180009614
0x18000960d  mov     r14d, dword ptr cs:qword_18007C418+4
0x180009614  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000961a  test    al, 10h
0x18000961c  jz      short loc_180009623
0x18000961e  and     eax, 1
0x180009621  jmp     short loc_180009628
0x180009623  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180009628  mov     edi, 0FFFFFFFFh
0x18000962d  test    eax, eax
0x18000962f  jz      short loc_1800096AF
0x180009631  cmp     cs:gWfpTrackHeapAllocs, esi
0x180009637  jz      short loc_180009679
0x180009639  mov     r8, [rbp+220h+lpMem]
0x18000963d  test    r8, r8
0x180009640  jz      short loc_18000967D
0x180009642  mov     eax, edi
0x180009644  lock xadd cs:gWfpNumHeapAllocs, eax
0x18000964c  cmp     eax, 1
0x18000964f  jns     short loc_180009679
0x180009651  cmp     cs:gMisalignedHeapTelemFired, esi
0x180009657  jnz     short loc_180009670
0x180009659  cmp     cs:gWfpNumHeapAllocs, esi
0x18000965f  jg      short loc_180009666
0x180009661  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009666  mov     cs:gMisalignedHeapTelemFired, 1
0x180009670  lock inc cs:gWfpNumHeapAllocs
0x180009677  jmp     short loc_1800096F7
0x180009679  mov     r8, [rbp+220h+lpMem]; lpMem
0x18000967d  mov     rcx, cs:gWfpHeap; hHeap
0x180009684  xor     edx, edx; dwFlags
0x180009686  call    cs:__imp_HeapFree
0x18000968d  nop     dword ptr [rax+rax+00h]
0x180009692  cmp     cs:gHeapFreeFailedFired, esi
0x180009698  jnz     short loc_1800096F7
0x18000969a  test    eax, eax
0x18000969c  jnz     short loc_1800096F7
0x18000969e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800096a3  mov     cs:gHeapFreeFailedFired, 1
0x1800096ad  jmp     short loc_1800096F7
0x1800096af  cmp     cs:gWfpTrackHeapBytes, esi
0x1800096b5  mov     r8, [rbp+220h+lpMem]; lpMem
0x1800096b9  jz      short loc_1800096E2
0x1800096bb  test    r8, r8
0x1800096be  jz      short loc_1800096E2
0x1800096c0  mov     rcx, cs:gWfpHeap; hHeap
0x1800096c7  xor     edx, edx; dwFlags
0x1800096c9  call    cs:__imp_HeapSize
0x1800096d0  nop     dword ptr [rax+rax+00h]
0x1800096d5  neg     eax
0x1800096d7  lock add cs:gWfpHeapBytesAllocated, eax
0x1800096de  mov     r8, [rbp+220h+lpMem]; lpMem
0x1800096e2  mov     rcx, cs:gWfpHeap; hHeap
0x1800096e9  xor     edx, edx; dwFlags
0x1800096eb  call    cs:__imp_HeapFree
0x1800096f2  nop     dword ptr [rax+rax+00h]
0x1800096f7  mov     rax, 0BADBADFABADBADFAh
0x180009701  mov     [rsp+320h+var_2C8], r12
0x180009706  lea     rcx, [rsp+320h+var_2C8]
0x18000970b  mov     [rbp+220h+lpMem], rax
0x18000970f  call    FwppSessionDestroy
0x180009714  mov     r12, [rsp+320h+var_20]
0x18000971c  test    rbx, rbx
0x18000971f  jz      short loc_180009735
0x180009721  lea     rdx, aFwpisnamecache; "FwpIsNameCacheEnabledForProcess"
0x180009728  mov     rcx, rbx
0x18000972b  call    WfpReportError
0x180009730  jmp     loc_180009938
0x180009735  test    r14d, r14d
0x180009738  jz      loc_180009938
0x18000973e  mov     r14, [rsp+320h+var_2B8]
0x180009743  test    r13d, r13d
0x180009746  jnz     loc_180009805
0x18000974c  test    r14, r14
0x18000974f  jnz     loc_180009805
0x180009755  mov     rcx, cs:WPP_GLOBAL_Control
0x18000975c  lea     rax, WPP_GLOBAL_Control
0x180009763  lea     rbx, aFwpmprocessnam_0; "FwpmProcessNameResolutionEvent0"
0x18000976a  cmp     rcx, rax
0x18000976d  jz      short loc_180009799
0x18000976f  cmp     byte ptr [rcx+19h], 2
0x180009773  jb      short loc_180009799
0x180009775  test    byte ptr [rcx+1Ch], 1
0x180009779  jz      short loc_180009799
0x18000977b  mov     rcx, [rcx+10h]
0x18000977f  mov     edx, 17h
0x180009784  mov     dword ptr [rsp+320h+var_2F8], 57h ; 'W'
0x18000978c  xor     r9d, r9d
0x18000978f  mov     [rsp+320h+var_300], rbx
0x180009794  call    WPP_SF_Ssd
0x180009799  cmp     cs:gWfpLogUserModeErrors, esi
0x18000979f  jz      short loc_1800097F9
0x1800097a1  test    cs:byte_18007C665, 1
0x1800097a8  jz      short loc_1800097F9
0x1800097aa  lea     rax, [rsp+320h+var_2D0]
0x1800097af  mov     dword ptr [rsp+320h+var_2D0], 57h ; 'W'
0x1800097b7  mov     [rbp+220h+var_108], rax
0x1800097be  lea     rdx, WFP_USERMODE_ERROR
0x1800097c5  lea     rax, [rbp+220h+var_128]
0x1800097cc  mov     [rbp+220h+var_118], rbx
0x1800097d3  mov     r9d, 3
0x1800097d9  mov     [rsp+320h+var_300], rax
0x1800097de  mov     [rbp+220h+var_110], 20h ; ' '
0x1800097e9  mov     [rbp+220h+var_100], 4
0x1800097f4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800097f9  mov     rbx, 0FFFFFFFF80070057h
0x180009800  jmp     loc_180009938
0x180009805  mov     r8, [rsp+320h+var_2A8]
0x18000980a  lea     r9, [rsp+320h+var_2C0]
0x18000980f  mov     rdx, r14
0x180009812  mov     ecx, r13d
0x180009815  call    FwpGetExpandedPeerName
0x18000981a  mov     r15, [rsp+320h+var_2C0]
0x18000981f  mov     rbx, rax
0x180009822  test    rax, rax
0x180009825  jnz     loc_180009938
0x18000982b  lea     r8, [rsp+320h+var_2D0]
0x180009830  mov     rdx, r15
0x180009833  lea     rcx, [rsp+320h+engineHandle]; engineHandle
0x180009838  call    FwpNameCacheGetEngineHandle
0x18000983d  mov     rbx, rax
0x180009840  test    rax, rax
0x180009843  jnz     loc_180009933
0x180009849  lea     rax, [rbp+220h+var_F0]
0x180009850  mov     [rbp+220h+var_1C0], 4
0x180009857  mov     ecx, r13d; netlong
0x18000985a  mov     [rbp+220h+var_1B8], rax
0x18000985e  call    cs:__imp_ntohl
0x180009865  nop     dword ptr [rax+rax+00h]
0x18000986a  mov     rsi, [rsp+320h+var_2D0]
0x18000986f  mov     r9, r15
0x180009872  mov     r8, [rbp+220h+var_2A0]
0x180009876  mov     ecx, eax
0x180009878  lea     rax, [rbp+220h+var_230]
0x18000987c  mov     rdx, r14
  ... truncated ...
```
