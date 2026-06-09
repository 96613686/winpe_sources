# CDXGISwapChain::ValidatePresent(SPresentArgsCore<CDXGISwapChainWrapper> const *,uint,tagRECT const *,uint,DXGI_SCROLL_RECT const *,DXGI_INTERNAL_CONTENT_PROTECTION const &,IDXGIResource *,bool &)

- ea: `0x18000d1f0`
- end: `0x18000dcc6`
- name: `?ValidatePresent@CDXGISwapChain@@QEAAJPEBU?$SPresentArgsCore@UCDXGISwapChainWrapper@@@@IPEBUtagRECT@@IPEBUDXGI_SCROLL_RECT@@AEBUDXGI_INTERNAL_CONTENT_PROTECTION@@PEAUIDXGIResource@@AEA_N@Z`
- size: `2774`
- prototype: `__int64 __usercall@<rax>(CDXGISwapChain *this@<rcx>, int, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008d40`

## callees

- `0x18000c6b0`
- `0x18000ce70`
- `0x18000d1f0`
- `0x180020ab0`
- `0x180057e40`
- `0x180070a4c`
- `0x1800714e0`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000d4c1`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000d7fa`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000d9cd`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000dbae`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000d4c1`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000d7fa`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000d9cd`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18000dbae`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18000d7e9`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18000d9b7`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18000db98`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18000d7e9`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18000d9b7`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x18000db98`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18000d7d4`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18000d99d`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18000d7d4`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18000d99d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x18000d44c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x18000d44c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDXGISwapChain::ValidatePresent(
        CDXGISwapChain *this,
        unsigned int *a2,
        unsigned int a3,
        const RECT *a4,
        unsigned int a5,
        __int64 a6,
        _DWORD *a7,
        __int64 a8,
        bool *a9)
{
  unsigned int v12; // r15d
  unsigned int v13; // esi
  unsigned int v14; // edi
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, RECT *); // rcx
  int v17; // ecx
  int v18; // ecx
  int v19; // edx
  __int64 result; // rax
  bool v21; // al
  bool v22; // zf
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // eax
  CModule *v28; // rcx
  unsigned int v29; // ecx
  __int64 i; // rdi
  unsigned int j; // edi
  const RECT *v32; // rsi
  int *v33; // r14
  __int64 v34; // rdx
  int *v35; // r15
  unsigned int v36; // ecx
  __int64 v37; // rdx
  __int64 v38; // rcx
  RECT rcSrc1; // [rsp+70h] [rbp-59h] BYREF
  RECT rc1; // [rsp+80h] [rbp-49h] BYREF
  struct tagRECT rcDst; // [rsp+90h] [rbp-39h] BYREF
  tagMONITORINFO mi; // [rsp+A0h] [rbp-29h] BYREF

  v12 = *a2;
  v13 = a2[2];
  v14 = a2[1];
  *a9 = 0;
  if ( v13 > 4 )
  {
    DXGI_SDK_MSG_SWAPCHAIN(*((struct IDXGIDebugProducer **)this + 38), DXGI_MSG_IDXGISwapChain_Present_SyncIntervalOOB);
    return 2289696769LL;
  }
  if ( *((_DWORD *)this + 82) == 1 )
  {
    v22 = (v14 & 0xFFFFFC00) == 0;
  }
  else
  {
    if ( (v14 & 0xFFFFFC80) == 0 )
      goto LABEL_4;
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapChain_Present_UnsupportedFlags,
      v14);
    if ( (unsigned __int8)CDXGISwapChain::IsFlipModel<1>(this) || v12 == 3 )
      return 2289696769LL;
    if ( !v12 )
      goto LABEL_4;
    v22 = v12 == 1;
  }
  if ( !v22 )
    return 2289696769LL;
LABEL_4:
  if ( (v14 & 1) != 0 && v14 != 1 )
  {
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapChain_Present_OtherFlagsCausingInvalidPresentTestFlag);
    if ( (unsigned __int8)CDXGISwapChain::IsFlipModel<1>(this) || v12 >= 2 )
      return 2289696769LL;
  }
  v15 = *((_DWORD *)this + 109);
  if ( (v15 & 1) != 0 && *((_DWORD *)this + 111) )
  {
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapChain_Present_InvalidNonPreRotatedFlag);
    return 2289696769LL;
  }
  v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, RECT *))*((_QWORD *)this + 220);
  if ( !v16 )
  {
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapChain_Present_NoAllocatedBuffers);
    return 2289696769LL;
  }
  if ( (v15 & 4) != 0 )
  {
    if ( !*((_DWORD *)this + 529) )
      goto LABEL_12;
    *(_QWORD *)&rcSrc1.left = 0;
    v27 = (**v16)(v16, &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea, &rcSrc1);
    if ( v27 )
      CModule::RecordJournalImpl(v28, v27, "Non-zero return value");
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&rcSrc1.left + 40LL))(*(_QWORD *)&rcSrc1.left) )
    {
      DXGI_SDK_MSG_SWAPCHAIN(*((struct IDXGIDebugProducer **)this + 38), DXGI_MSG_IDXGISwapChain_Present_UnreleasedHDC);
LABEL_26:
      if ( *(_QWORD *)&rcSrc1.left )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rcSrc1.left + 16LL))(*(_QWORD *)&rcSrc1.left);
      return 2289696769LL;
    }
    if ( *(_QWORD *)&rcSrc1.left )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rcSrc1.left + 16LL))(*(_QWORD *)&rcSrc1.left);
  }
  if ( *((_DWORD *)this + 529) )
  {
    *(_QWORD *)&rcSrc1.left = 0;
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, RECT *))this + 220))(
           *((_QWORD *)this + 220),
           &GUID_9264d6b2_8b0b_4595_a5c4_4eebfbd3b69d,
           &rcSrc1) >= 0
      && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&rcSrc1.left + 24LL))(*(_QWORD *)&rcSrc1.left) )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGIFactory_CheckFeatureSupport_InvalidSize|DXGI_MSG_IDXGISwapChain_GetDesc_pDescIsNULL);
      goto LABEL_26;
    }
    if ( *(_QWORD *)&rcSrc1.left )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rcSrc1.left + 16LL))(*(_QWORD *)&rcSrc1.left);
  }
LABEL_12:
  if ( (v14 & 0x200) != 0 )
  {
    if ( !*((_DWORD *)this + 111) )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_FullscreenAllowTearingIsInvalid);
      return 2289696769LL;
    }
    if ( v13 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_AllowTearingRequiresPresentIntervalZero);
      return 2289696769LL;
    }
    if ( (*((_DWORD *)this + 109) & 0x800) == 0 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_AllowTearingRequiresCreationFlag);
      return 2289696769LL;
    }
  }
  if ( (v14 & 2) != 0 && !*((_DWORD *)this + 178) )
  {
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapChain_Present_DoNotSequenceFlagSetButPreviousBufferIsUndefined);
    v25 = *((_DWORD *)this + 107);
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        if ( (unsigned int)(v26 - 2) < 2 )
          return 2289696769LL;
      }
    }
    if ( v12 >= 2 )
      return 2289696769LL;
  }
  v17 = *((_DWORD *)this + 107);
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( v18 )
    {
      if ( (unsigned int)(v18 - 2) < 2 && (*((_BYTE *)this + 940) & 4) == 0 )
      {
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapChain_Present_FlipModelChainMustResizeOrCreateOnFSTransition);
        return 2289696769LL;
      }
    }
  }
  v19 = *((_DWORD *)this + 111);
  if ( v19 != 1 && *((_DWORD *)this + 424) != 1 )
  {
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapchain_Present_FullscreenRotation);
    return 2289696769LL;
  }
  if ( (v14 & 0x20) != 0 )
  {
    if ( (v14 & 0x10) != 0 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_TemporaryMonoAndPreferRight);
      return 2289696769LL;
    }
  }
  else if ( (v14 & 0x10) == 0 )
  {
    goto LABEL_21;
  }
  if ( !*((_DWORD *)this + 101) )
  {
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapChain_Present_TemporaryMonoOrPreferRightWithoutStereo);
    return 2289696769LL;
  }
  if ( (v14 & 0x20) != 0 && (!*((_BYTE *)this + 1964) || v19 != 1 && !*((_BYTE *)this + 2096)) )
  {
    DXGI_SDK_MSG_SWAPCHAIN(
      *((struct IDXGIDebugProducer **)this + 38),
      DXGI_MSG_IDXGISwapChain_Present_TemporaryMonoUnsupported);
    return 2289696769LL;
  }
LABEL_21:
  if ( (*((_DWORD *)this + 109) & 0x1000) == 0 && (v14 & 0x40) != 0 )
  {
    if ( !*((_QWORD *)this + 267) )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_RestrictToOutputFlagSetButInvalidpRestrictToOutput);
      return 2289696769LL;
    }
    if ( !*(_BYTE *)(*((_QWORD *)this + 29) + 436LL) )
    {
      memset(&mi, 0, sizeof(mi));
      mi.cbSize = 40;
      if ( !GetMonitorInfoW(*((HMONITOR *)this + 268), &mi) )
      {
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapChain_Present_RestrictOutputFlagWithStaleSwapChain);
        return 2289696809LL;
      }
    }
    if ( !*((_DWORD *)this + 111) )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_RestrictToOutputFlagdWithFullscreen);
      return 2289696769LL;
    }
    if ( CDXGISwapChain::IsDwmVailSwapChain(this)
      && (unsigned __int8)CTelemetryThrottler<2>::IsEnabled(qword_180108338, 1) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v38);
    }
  }
  if ( (v14 & 4) != 0 && *((_DWORD *)this + 111) == 1 )
  {
    v23 = *((_DWORD *)this + 107);
    if ( !v23 || (v24 = v23 - 1) == 0 || (unsigned int)(v24 - 2) >= 2 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_RestartIsFullscreenOnly);
      if ( v12 >= 2 )
        return 2289696769LL;
    }
  }
  if ( (a3 || a5) && *((_DWORD *)this + 82) > 1u )
  {
    *(_QWORD *)&rc1.left = 0;
    rc1.right = *((_DWORD *)this + 94);
    rc1.bottom = *((_DWORD *)this + 95);
    v21 = a3 == 1 && EqualRect(&rc1, a4) && !a5;
    *a9 = v21;
    if ( !*((_DWORD *)this + 178) && !v21 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_PartialPresentationBeforeStandardPresentation);
      return 2289696769LL;
    }
    if ( ((*((_BYTE *)this + 440) & 4) != 0 || (*((_DWORD *)this + 109) & 0x200) != 0) && !v21 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_PartialPresentation_YUV);
      return 2289696769LL;
    }
    if ( *((_DWORD *)this + 111) != 1 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_FullscreenPartialPresentIsInvalid);
      return 2289696769LL;
    }
    if ( (v14 & 3) != 0 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_InvalidPresentTestOrDoNotSequenceFlag,
        v14);
      return 2289696769LL;
    }
    if ( *((_DWORD *)this + 102) != 1 || *((_DWORD *)this + 103) )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_PartialPresentationWithMSAABuffers);
      return 2289696769LL;
    }
    v29 = *((_DWORD *)this + 107);
    if ( (!v29 || v29 != 1 && v29 != 3) && a3 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_PartialPresentationWithSwapEffectDiscard);
      return 2289696769LL;
    }
    if ( v29 < 2 || v29 - 3 >= 2 || (v36 = v29 - 1) != 0 && v36 != 2 )
    {
      if ( a5 )
      {
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapchain_Present_ScrollUnsupported);
        return 2289696769LL;
      }
    }
    else if ( a5 && !a3 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_ScrollInfoWithNoDirtyRectsSpecified);
    }
    rcDst = 0;
    for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(i + 1) )
    {
      v33 = (int *)(a6 + 24 * i);
      if ( IsRectEmpty((const RECT *)(v33 + 2)) )
      {
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapChain_Present_EmptyScrollRect,
          (unsigned int)i,
          (unsigned int)v33[2],
          v33[3],
          v33[4],
          v33[5]);
        return 2289696769LL;
      }
      if ( !IntersectRect(&rcDst, (const RECT *)(v33 + 2), &rc1) || !EqualRect(&rcDst, (const RECT *)(v33 + 2)) )
      {
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapChain_Present_ScrollRectOutOfBackbufferBounds,
          (unsigned int)i,
          (unsigned int)v33[2],
          v33[3],
          v33[4],
          v33[5],
          *((_DWORD *)this + 94),
          *((_DWORD *)this + 95));
        return 2289696769LL;
      }
      rcSrc1 = 0;
      v34 = *v33;
      v35 = v33 + 4;
      if ( (unsigned __int64)(v33[2] - v34 + 0x80000000LL) > 0xFFFFFFFF )
      {
        rcSrc1.left = -1;
LABEL_138:
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapChain_Present_ScrollRectOutOfBackbufferBoundsWithOffset,
          (unsigned int)i,
          (unsigned int)v33[2],
          v33[3],
          *v35,
          v33[5],
          *v33,
          v33[1],
          *((_DWORD *)this + 94),
          *((_DWORD *)this + 95));
        return 2289696769LL;
      }
      rcSrc1.left = v33[2] - v34;
      if ( (unsigned __int64)(*v35 - v34 + 0x80000000LL) > 0xFFFFFFFF )
      {
        rcSrc1.right = -1;
        goto LABEL_138;
      }
      rcSrc1.right = *v35 - v34;
      v37 = v33[1];
      if ( (unsigned __int64)(v33[3] - v37 + 0x80000000LL) > 0xFFFFFFFF )
      {
        rcSrc1.top = -1;
        goto LABEL_138;
      }
      rcSrc1.top = v33[3] - v37;
      if ( (unsigned __int64)(v33[5] - v37 + 0x80000000LL) > 0xFFFFFFFF )
      {
        rcSrc1.bottom = -1;
        goto LABEL_138;
      }
      rcSrc1.bottom = v33[5] - v37;
      if ( !IntersectRect(&rcDst, &rcSrc1, &rc1) || !EqualRect(&rcDst, &rcSrc1) )
        goto LABEL_138;
    }
    for ( j = 0; j < a3; ++j )
    {
      v32 = &a4[j];
      if ( IsRectEmpty(v32) )
      {
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapChain_Present_EmptyDirtyRect,
          j,
          (unsigned int)v32->left,
          v32->top,
          v32->right,
          v32->bottom);
        return 2289696769LL;
      }
      if ( !IntersectRect(&rcDst, v32, &rc1) || !EqualRect(&rcDst, v32) )
      {
        DXGI_SDK_MSG_SWAPCHAIN(
          *((struct IDXGIDebugProducer **)this + 38),
          DXGI_MSG_IDXGISwapChain_Present_DirtyRectOutOfBackbufferBounds,
          j,
          (unsigned int)v32->left,
          v32->top,
          v32->right,
          v32->bottom,
          *((_DWORD *)this + 94),
          *((_DWORD *)this + 95));
        return 2289696769LL;
      }
    }
  }
  if ( (*a7 & 1) == 0 )
    goto LABEL_31;
  if ( *((_DWORD *)this + 111) )
  {
    if ( (*a7 & 2) != 0 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_ProtectedContentInWindowedModeWithoutFSOrOverlay);
      return 2289696810LL;
    }
    if ( !(unsigned __int8)CDXGISwapChain::IsFlipModel<1>(this) )
    {
      DXGI_SDK_MSG_SWAPCHAIN(
        *((struct IDXGIDebugProducer **)this + 38),
        DXGI_MSG_IDXGISwapChain_Present_ProtectedContentInWindowedModeWithoutFlipSequential);
      return 2289696810LL;
    }
  }
  if ( *((_BYTE *)this + 2530) || *((_BYTE *)this + 2529) )
    return 2289696810LL;
LABEL_31:
  if ( !a8 )
    return 0;
  if ( *((_QWORD *)this + 238) || *((_DWORD *)this + 82) || !*((_BYTE *)this + 2102) )
    return 2289696769LL;
  result = 0;
  if ( *((_DWORD *)this + 107) != 1 )
    return 2289696769LL;
  return result;
}

```

## disassembly

```asm
0x18000d1f0  mov     [rsp-8+arg_10], rbx
0x18000d1f5  push    rbp
0x18000d1f6  push    rsi
0x18000d1f7  push    rdi
0x18000d1f8  push    r12
0x18000d1fa  push    r13
0x18000d1fc  push    r14
0x18000d1fe  push    r15
0x18000d200  lea     rbp, [rsp-7]
0x18000d205  sub     rsp, 0D0h
0x18000d20c  mov     rax, cs:__security_cookie
0x18000d213  xor     rax, rsp
0x18000d216  mov     [rbp+37h+var_38], rax
0x18000d21a  mov     r12, r9
0x18000d21d  mov     [rbp+37h+var_98], r9
0x18000d221  mov     r13d, r8d
0x18000d224  mov     rbx, rcx
0x18000d227  mov     rax, [rbp+37h+arg_28]
0x18000d22b  mov     [rbp+37h+var_A0], rax
0x18000d22f  mov     r14, [rbp+37h+arg_40]
0x18000d236  mov     r15d, [rdx]
0x18000d239  mov     esi, [rdx+8]
0x18000d23c  mov     edi, [rdx+4]
0x18000d23f  mov     byte ptr [r14], 0
0x18000d243  cmp     esi, 4
0x18000d246  ja      loc_18000D8D8
0x18000d24c  cmp     dword ptr [rcx+148h], 1
0x18000d253  jz      loc_18000D542
0x18000d259  mov     r9d, edi
0x18000d25c  and     r9d, 0FFFFFC80h
0x18000d263  jnz     loc_18000D8EE
0x18000d269  test    dil, 1
0x18000d26d  jnz     loc_18000D56E
0x18000d273  mov     eax, [rbx+1B4h]
0x18000d279  test    al, 1
0x18000d27b  jnz     loc_18000D553
0x18000d281  mov     rcx, [rbx+6E0h]
0x18000d288  test    rcx, rcx
0x18000d28b  jz      loc_18000D8AD
0x18000d291  test    al, 4
0x18000d293  jnz     loc_18000D6DA
0x18000d299  cmp     dword ptr [rbx+844h], 0
0x18000d2a0  jz      short loc_18000D2E5
0x18000d2a2  mov     qword ptr [rbp+37h+rcSrc1.left], 0
0x18000d2aa  mov     rcx, [rbx+6E0h]
0x18000d2b1  mov     rax, [rcx]
0x18000d2b4  lea     r8, [rbp+37h+rcSrc1]
0x18000d2b8  lea     rdx, _GUID_9264d6b2_8b0b_4595_a5c4_4eebfbd3b69d
0x18000d2bf  mov     rax, [rax]
0x18000d2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2c7  test    eax, eax
0x18000d2c9  jns     loc_18000D387
0x18000d2cf  mov     rcx, qword ptr [rbp+37h+rcSrc1.left]
0x18000d2d3  test    rcx, rcx
0x18000d2d6  jz      short loc_18000D2E5
0x18000d2d8  mov     rax, [rcx]
0x18000d2db  mov     rax, [rax+10h]
0x18000d2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2e4  nop
0x18000d2e5  bt      edi, 9
0x18000d2e9  jb      loc_18000D640
0x18000d2ef  test    dil, 2
0x18000d2f3  jnz     loc_18000D66F
0x18000d2f9  mov     ecx, [rbx+1ACh]
0x18000d2ff  test    ecx, ecx
0x18000d301  jz      short loc_18000D31A
0x18000d303  sub     ecx, 1
0x18000d306  jz      short loc_18000D31A
0x18000d308  sub     ecx, 2
0x18000d30b  jz      loc_18000DA08
0x18000d311  cmp     ecx, 1
0x18000d314  jz      loc_18000DA08
0x18000d31a  mov     edx, [rbx+1BCh]
0x18000d320  cmp     edx, 1
0x18000d323  jz      short loc_18000D332
0x18000d325  cmp     dword ptr [rbx+6A0h], 1
0x18000d32c  jnz     loc_18000D6D0
0x18000d332  mov     eax, edi
0x18000d334  and     eax, 20h
0x18000d337  test    dil, 10h
0x18000d33b  jnz     loc_18000DBC3
0x18000d341  xor     cl, cl
0x18000d343  test    eax, eax
0x18000d345  jnz     loc_18000DBCA
0x18000d34b  test    cl, cl
0x18000d34d  jnz     loc_18000D976
0x18000d353  test    dword ptr [rbx+1B4h], 1000h
0x18000d35d  setz    cl
0x18000d360  test    dil, 40h
0x18000d364  setnz   al
0x18000d367  test    al, cl
0x18000d369  jz      loc_18000D477
0x18000d36f  cmp     qword ptr [rbx+858h], 0
0x18000d377  jnz     loc_18000D419
0x18000d37d  mov     edx, 78h ; 'x'
0x18000d382  jmp     loc_18000D52C
0x18000d387  mov     rcx, qword ptr [rbp+37h+rcSrc1.left]
0x18000d38b  mov     rax, [rcx]
0x18000d38e  mov     rax, [rax+18h]
0x18000d392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d397  test    eax, eax
0x18000d399  jz      loc_18000D2CF
0x18000d39f  mov     edx, 128h; enum DXGI_Message_Id
0x18000d3a4  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x18000d3ab  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x18000d3b0  nop
0x18000d3b1  mov     rcx, qword ptr [rbp+37h+rcSrc1.left]
0x18000d3b5  test    rcx, rcx
0x18000d3b8  jz      short loc_18000D3C7
0x18000d3ba  mov     rax, [rcx]
0x18000d3bd  mov     rax, [rax+10h]
0x18000d3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c6  nop
0x18000d3c7  mov     eax, 887A0001h
0x18000d3cc  jmp     short loc_18000D3F2
0x18000d3ce  test    esi, esi
0x18000d3d0  jnz     loc_18000D48D
0x18000d3d6  mov     rax, [rbp+37h+arg_30]
0x18000d3da  mov     ecx, [rax]
0x18000d3dc  test    cl, 1
0x18000d3df  jnz     loc_18000DC73
0x18000d3e5  cmp     [rbp+37h+arg_38], 0
0x18000d3ea  jnz     loc_18000D938
0x18000d3f0  xor     eax, eax
0x18000d3f2  mov     rcx, [rbp+37h+var_38]
0x18000d3f6  xor     rcx, rsp; StackCookie
0x18000d3f9  call    __security_check_cookie
0x18000d3fe  mov     rbx, [rsp+100h+arg_10]
0x18000d406  add     rsp, 0D0h
0x18000d40d  pop     r15
0x18000d40f  pop     r14
0x18000d411  pop     r13
0x18000d413  pop     r12
0x18000d415  pop     rdi
0x18000d416  pop     rsi
0x18000d417  pop     rbp
0x18000d418  retn
0x18000d419  mov     rax, [rbx+0E8h]
0x18000d420  cmp     byte ptr [rax+1B4h], 0
0x18000d427  jnz     short loc_18000D45A
0x18000d429  xorps   xmm0, xmm0
0x18000d42c  xor     eax, eax
0x18000d42e  movups  xmmword ptr [rbp+37h+mi.cbSize], xmm0
0x18000d432  movups  xmmword ptr [rbp+37h+mi.rcMonitor.bottom], xmm0
0x18000d436  mov     qword ptr [rbp+37h+mi.rcWork.bottom], rax
0x18000d43a  mov     [rbp+37h+mi.cbSize], 28h ; '('
0x18000d441  lea     rdx, [rbp+37h+mi]; lpmi
0x18000d445  mov     rcx, [rbx+860h]; hMonitor
0x18000d44c  call    cs:__imp_GetMonitorInfoW
0x18000d452  test    eax, eax
0x18000d454  jz      loc_18000D892
0x18000d45a  cmp     dword ptr [rbx+1BCh], 0
0x18000d461  jz      loc_18000D888
0x18000d467  mov     rcx, rbx; this
0x18000d46a  call    ?IsDwmVailSwapChain@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsDwmVailSwapChain(void)
0x18000d46f  test    al, al
0x18000d471  jnz     loc_18000DBDC
0x18000d477  test    dil, 4
0x18000d47b  jnz     loc_18000D5BE
0x18000d481  mov     esi, [rbp+37h+arg_20]
0x18000d484  test    r13d, r13d
0x18000d487  jz      loc_18000D3CE
0x18000d48d  cmp     dword ptr [rbx+148h], 1
0x18000d494  jbe     loc_18000D3D6
0x18000d49a  mov     qword ptr [rbp+37h+rc1.left], 0
0x18000d4a2  mov     eax, [rbx+178h]
0x18000d4a8  mov     [rbp+37h+rc1.right], eax
0x18000d4ab  mov     eax, [rbx+17Ch]
0x18000d4b1  mov     [rbp+37h+rc1.bottom], eax
0x18000d4b4  cmp     r13d, 1
0x18000d4b8  jnz     short loc_18000D4CF
0x18000d4ba  mov     rdx, r12; lprc2
0x18000d4bd  lea     rcx, [rbp+37h+rc1]; lprc1
0x18000d4c1  call    cs:__imp_EqualRect
0x18000d4c7  test    eax, eax
0x18000d4c9  jnz     loc_18000D631
0x18000d4cf  xor     al, al
0x18000d4d1  mov     [r14], al
0x18000d4d4  cmp     dword ptr [rbx+2C8h], 0
0x18000d4db  jz      loc_18000D61F
0x18000d4e1  test    byte ptr [rbx+1B8h], 4
0x18000d4e8  jnz     loc_18000DBFF
0x18000d4ee  test    dword ptr [rbx+1B4h], 200h
0x18000d4f8  jnz     loc_18000DBFF
0x18000d4fe  cmp     dword ptr [rbx+1BCh], 1
0x18000d505  jnz     short loc_18000D567
0x18000d507  test    dil, 3
0x18000d50b  jnz     loc_18000DC11
0x18000d511  cmp     dword ptr [rbx+198h], 1
0x18000d518  jnz     short loc_18000D527
0x18000d51a  cmp     dword ptr [rbx+19Ch], 0
0x18000d521  jz      loc_18000D74A
0x18000d527  mov     edx, 9Bh; enum DXGI_Message_Id
0x18000d52c  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x18000d533  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x18000d538  mov     eax, 887A0001h
0x18000d53d  jmp     loc_18000D3F2
0x18000d542  test    edi, 0FFFFFC00h
0x18000d548  jz      loc_18000D269
0x18000d54e  jmp     loc_18000D3C7
0x18000d553  cmp     dword ptr [rbx+1BCh], 0
0x18000d55a  jz      loc_18000D281
0x18000d560  mov     edx, 0Fh
0x18000d565  jmp     short loc_18000D52C
0x18000d567  mov     edx, 6Ah ; 'j'
0x18000d56c  jmp     short loc_18000D52C
0x18000d56e  mov     r8d, edi
0x18000d571  xor     r8d, 1
0x18000d575  jz      loc_18000D273
0x18000d57b  mov     edx, 7Bh ; '{'; enum DXGI_Message_Id
0x18000d580  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x18000d587  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x18000d58c  mov     rcx, rbx
0x18000d58f  call    ??$IsFlipModel@$00@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsFlipModel<1>(void)
0x18000d594  test    al, al
0x18000d596  jnz     loc_18000D3C7
0x18000d59c  cmp     r15d, 3
0x18000d5a0  jz      loc_18000D3C7
0x18000d5a6  test    r15d, r15d
0x18000d5a9  jz      loc_18000D273
0x18000d5af  cmp     r15d, 1
0x18000d5b3  jz      loc_18000D273
0x18000d5b9  jmp     loc_18000D3C7
0x18000d5be  cmp     dword ptr [rbx+1BCh], 1
0x18000d5c5  jnz     loc_18000D481
0x18000d5cb  mov     ecx, [rbx+1ACh]
0x18000d5d1  test    ecx, ecx
0x18000d5d3  jz      short loc_18000D5EC
0x18000d5d5  sub     ecx, 1
0x18000d5d8  jz      short loc_18000D5EC
0x18000d5da  sub     ecx, 2
0x18000d5dd  jz      loc_18000D481
0x18000d5e3  cmp     ecx, 1
0x18000d5e6  jz      loc_18000D481
0x18000d5ec  mov     edx, 91h; enum DXGI_Message_Id
0x18000d5f1  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x18000d5f8  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x18000d5fd  cmp     r15d, 3
0x18000d601  jz      loc_18000D3C7
0x18000d607  test    r15d, r15d
0x18000d60a  jz      loc_18000D481
0x18000d610  cmp     r15d, 1
0x18000d614  jz      loc_18000D481
0x18000d61a  jmp     loc_18000D3C7
0x18000d61f  test    al, al
0x18000d621  jnz     loc_18000D4E1
0x18000d627  mov     edx, 69h ; 'i'
0x18000d62c  jmp     loc_18000D52C
0x18000d631  test    esi, esi
0x18000d633  jnz     loc_18000D4CF
0x18000d639  mov     al, 1
0x18000d63b  jmp     loc_18000D4D1
0x18000d640  cmp     dword ptr [rbx+1BCh], 0
0x18000d647  jz      loc_18000D8B7
0x18000d64d  test    esi, esi
0x18000d64f  jnz     loc_18000D92E
0x18000d655  test    dword ptr [rbx+1B4h], 800h
0x18000d65f  jnz     loc_18000D2EF
0x18000d665  mov     edx, 11Ch
0x18000d66a  jmp     loc_18000D52C
0x18000d66f  cmp     dword ptr [rbx+2C8h], 0
0x18000d676  jnz     loc_18000D2F9
0x18000d67c  mov     edx, 73h ; 's'; enum DXGI_Message_Id
0x18000d681  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x18000d688  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x18000d68d  mov     ecx, [rbx+1ACh]
0x18000d693  test    ecx, ecx
0x18000d695  jz      short loc_18000D6AE
0x18000d697  sub     ecx, 1
0x18000d69a  jz      short loc_18000D6AE
0x18000d69c  sub     ecx, 2
0x18000d69f  jz      loc_18000D3C7
0x18000d6a5  cmp     ecx, 1
0x18000d6a8  jz      loc_18000D3C7
0x18000d6ae  cmp     r15d, 3
0x18000d6b2  jz      loc_18000D3C7
0x18000d6b8  test    r15d, r15d
0x18000d6bb  jz      loc_18000D2F9
0x18000d6c1  cmp     r15d, 1
0x18000d6c5  jz      loc_18000D2F9
0x18000d6cb  jmp     loc_18000D3C7
0x18000d6d0  mov     edx, 9Ah
0x18000d6d5  jmp     loc_18000D52C
0x18000d6da  cmp     dword ptr [rbx+844h], 0
0x18000d6e1  jz      loc_18000D2E5
0x18000d6e7  mov     qword ptr [rbp+37h+rcSrc1.left], 0
0x18000d6ef  mov     rax, [rcx]
0x18000d6f2  lea     r8, [rbp+37h+rcSrc1]
0x18000d6f6  lea     rdx, _GUID_79d2046c_22ef_451b_9e74_2245d9c760ea
0x18000d6fd  mov     rax, [rax]
0x18000d700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d705  test    eax, eax
0x18000d707  jz      short loc_18000D717
0x18000d709  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x18000d710  mov     edx, eax; unsigned int
0x18000d712  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18000d717  mov     rcx, qword ptr [rbp+37h+rcSrc1.left]
0x18000d71b  mov     rax, [rcx]
0x18000d71e  mov     rax, [rax+28h]
0x18000d722  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
