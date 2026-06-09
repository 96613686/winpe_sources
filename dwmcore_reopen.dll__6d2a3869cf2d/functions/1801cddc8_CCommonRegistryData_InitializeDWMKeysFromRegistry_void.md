# CCommonRegistryData::InitializeDWMKeysFromRegistry(void)

- ea: `0x1801cddc8`
- end: `0x1801ce3dc`
- name: `?InitializeDWMKeysFromRegistry@CCommonRegistryData@@CAXXZ`
- size: `1556`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801cdd10`

## callees

- `0x1801cddc8`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cde1f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cde5c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cde8c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdece`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdf10`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdf4f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdf9b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdfda`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce044`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce08b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce0da`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce120`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce159`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce192`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce1f7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce22f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce27e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce2ae`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce2eb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce328`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cde1f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cde5c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cde8c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdece`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdf10`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdf4f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdf9b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cdfda`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce044`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce08b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce0da`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce120`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce159`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce192`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce1f7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce22f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce27e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce2ae`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce2eb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801ce328`

## string_xrefs

- `0x1801ce0f5`: `CompositorClockPolicy`

## pseudocode

```c
void CCommonRegistryData::InitializeDWMKeysFromRegistry(void)
{
  LONGLONG v0; // rcx
  LONGLONG v1; // rdx
  unsigned int v2; // eax
  int v3; // eax
  unsigned int v4; // [rsp+70h] [rbp+30h] BYREF

  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"OverlayTestMode",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_dwOverlayTestMode = v4;
  v4 = 0;
  GetPersistedRegistryValueW(
    L"DWMSwitches",
    L"Software\\Microsoft\\Windows\\Dwm",
    L"DisableAdvancedDirectFlip",
    16,
    0,
    &v4,
    4,
    0);
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"DisableIndependentFlip",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_fDisableIndependentFlip = v4 != 0;
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"FrameCounterPosition",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_fDebugFrameCounterIsVertical = v4 != 0;
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"FlattenVirtualSurfaceEffectInput",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_fFlattenVirtualSurfaceBrush = v4 != 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"CpuClipFlatteningTolerance",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_flCpuClipFlatteningTolerance = (float)(int)v4 / 1000.0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"InteractionOutputPredictionDisabled",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_fDisableInteractionOutputPrediction = v4 != 0;
  if ( (unsigned int)GetPersistedRegistryValueW(
                       L"DWMSwitches",
                       L"Software\\Microsoft\\Windows\\Dwm",
                       L"BackdropBlurCachingThrottleMs",
                       16,
                       0,
                       &v4,
                       4,
                       0) )
  {
    v0 = 25 * g_qpcFrequency.QuadPart;
  }
  else
  {
    v2 = v4;
    if ( v4 > 0x3E8 )
      v2 = 1000;
    v0 = g_qpcFrequency.QuadPart * v2;
  }
  v4 = 0;
  CCommonRegistryData::m_backdropBlurCachingThrottleQPCTimeDelta = v0 / 1000;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSceneSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm\\Scene",
                        L"ForceNonPrimaryDisplayAdapter",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_fSceneForceNonPrimaryDisplayAdapter = v4 != 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSceneSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm\\Scene",
                        L"ImageProcessingResizeThreshold",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_flSceneImageProcessingResizeThreshold = (float)(int)v4 / 100.0;
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"ForceEffectMode",
                        16,
                        0,
                        &v4,
                        4,
                        0)
    && v4 <= 2 )
  {
    CCommonRegistryData::m_forceEffectMode = v4;
  }
  CCommonRegistryData::m_compositorClockPolicy = 1;
  v4 = 1;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"CompositorClockPolicy",
                        16,
                        0,
                        &v4,
                        4,
                        0)
    && v4 < 2 )
  {
    CCommonRegistryData::m_compositorClockPolicy = v4;
  }
  v4 = 1;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"ParallelModePolicy",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
  {
    v3 = v4;
    if ( v4 >= 3 )
      v3 = 1;
    CCommonRegistryData::m_parallelModePolicy = v3;
  }
  v4 = 1;
  if ( (unsigned int)GetPersistedRegistryValueW(
                       L"DWMSwitches",
                       L"Software\\Microsoft\\Windows\\Dwm",
                       L"ParallelModeRateThreshold",
                       16,
                       0,
                       &v4,
                       4,
                       0) )
  {
    v1 = g_qpcFrequency.QuadPart / 119;
  }
  else if ( v4 )
  {
    v1 = g_qpcFrequency.QuadPart / v4;
  }
  else
  {
    v1 = 0;
  }
  CCommonRegistryData::m_parallelModeDurationThreshold = v1;
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"CustomRefreshRateMode",
                        16,
                        0,
                        &v4,
                        4,
                        0)
    && v4 <= 2 )
  {
    CCommonRegistryData::m_customRefreshRateMode = v4;
  }
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"SDRBoostPercentOverride",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_flSDRBoostOverride = (float)(int)v4 / 100.0;
  v4 = 0;
  GetPersistedRegistryValueW(
    L"DWMSwitches",
    L"Software\\Microsoft\\Windows\\Dwm",
    L"DisableProjectedShadowsRendering",
    16,
    0,
    &v4,
    4,
    0);
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"ShowDirtyRegions",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_fShowDirtyRegions = v4;
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"ResampleModeOverride",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_dwResampleModeOverride = v4;
  v4 = 0;
  if ( !(unsigned int)GetPersistedRegistryValueW(
                        L"DWMSwitches",
                        L"Software\\Microsoft\\Windows\\Dwm",
                        L"ResampleInLinearSpace",
                        16,
                        0,
                        &v4,
                        4,
                        0) )
    CCommonRegistryData::m_fResampleInLinearSpace = v4;
}

```

## disassembly

```asm
0x1801cddc8  mov     r11, rsp
0x1801cddcb  mov     [r11+10h], rbx
0x1801cddcf  mov     [r11+18h], rsi
0x1801cddd3  push    rbp
0x1801cddd4  push    rdi
0x1801cddd5  push    r12
0x1801cddd7  push    r14
0x1801cddd9  push    r15
0x1801cdddb  mov     rbp, rsp
0x1801cddde  sub     rsp, 40h
0x1801cdde2  xor     ebx, ebx
0x1801cdde4  lea     rax, [rbp+arg_0]
0x1801cdde8  mov     [r11-30h], rbx
0x1801cddec  lea     r14, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Dwm"
0x1801cddf3  lea     r15, aDwmswitches; "DWMSwitches"
0x1801cddfa  mov     [rbp+arg_0], ebx
0x1801cddfd  lea     r8, aOverlaytestmod; "OverlayTestMode"
0x1801cde04  mov     rdx, r14
0x1801cde07  lea     edi, [rbx+4]
0x1801cde0a  mov     rcx, r15
0x1801cde0d  mov     [rsp+40h+var_10], edi
0x1801cde11  lea     esi, [rbx+10h]
0x1801cde14  mov     [r11-40h], rax
0x1801cde18  mov     r9d, esi
0x1801cde1b  mov     [r11-48h], rbx
0x1801cde1f  call    cs:__imp_GetPersistedRegistryValueW
0x1801cde25  test    eax, eax
0x1801cde27  jnz     short loc_1801CDE32
0x1801cde29  mov     eax, [rbp+arg_0]
0x1801cde2c  mov     cs:?m_dwOverlayTestMode@CCommonRegistryData@@0KA, eax; ulong CCommonRegistryData::m_dwOverlayTestMode
0x1801cde32  mov     [rsp+40h+var_8], rbx
0x1801cde37  lea     rax, [rbp+arg_0]
0x1801cde3b  mov     [rsp+40h+var_10], edi
0x1801cde3f  lea     r8, aDisableadvance; "DisableAdvancedDirectFlip"
0x1801cde46  mov     [rsp+40h+var_18], rax
0x1801cde4b  mov     r9d, esi
0x1801cde4e  mov     rdx, r14
0x1801cde51  mov     [rsp+40h+var_20], rbx
0x1801cde56  mov     rcx, r15
0x1801cde59  mov     [rbp+arg_0], ebx
0x1801cde5c  call    cs:__imp_GetPersistedRegistryValueW
0x1801cde62  mov     [rsp+40h+var_8], rbx
0x1801cde67  lea     rax, [rbp+arg_0]
0x1801cde6b  mov     [rsp+40h+var_10], edi
0x1801cde6f  lea     r8, aDisableindepen; "DisableIndependentFlip"
0x1801cde76  mov     [rsp+40h+var_18], rax
0x1801cde7b  mov     r9d, esi
0x1801cde7e  mov     rdx, r14
0x1801cde81  mov     [rsp+40h+var_20], rbx
0x1801cde86  mov     rcx, r15
0x1801cde89  mov     [rbp+arg_0], ebx
0x1801cde8c  call    cs:__imp_GetPersistedRegistryValueW
0x1801cde92  test    eax, eax
0x1801cde94  jnz     short loc_1801CDEA4
0x1801cde96  cmp     [rbp+arg_0], ebx
0x1801cde99  mov     eax, ebx
0x1801cde9b  setnz   al
0x1801cde9e  mov     cs:?m_fDisableIndependentFlip@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDisableIndependentFlip
0x1801cdea4  mov     [rsp+40h+var_8], rbx
0x1801cdea9  lea     rax, [rbp+arg_0]
0x1801cdead  mov     [rsp+40h+var_10], edi
0x1801cdeb1  lea     r8, aFramecounterpo; "FrameCounterPosition"
0x1801cdeb8  mov     [rsp+40h+var_18], rax
0x1801cdebd  mov     r9d, esi
0x1801cdec0  mov     rdx, r14
0x1801cdec3  mov     [rsp+40h+var_20], rbx
0x1801cdec8  mov     rcx, r15
0x1801cdecb  mov     [rbp+arg_0], ebx
0x1801cdece  call    cs:__imp_GetPersistedRegistryValueW
0x1801cded4  test    eax, eax
0x1801cded6  jnz     short loc_1801CDEE6
0x1801cded8  cmp     [rbp+arg_0], ebx
0x1801cdedb  mov     eax, ebx
0x1801cdedd  setnz   al
0x1801cdee0  mov     cs:?m_fDebugFrameCounterIsVertical@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDebugFrameCounterIsVertical
0x1801cdee6  mov     [rsp+40h+var_8], rbx
0x1801cdeeb  lea     rax, [rbp+arg_0]
0x1801cdeef  mov     [rsp+40h+var_10], edi
0x1801cdef3  lea     r8, aFlattenvirtual; "FlattenVirtualSurfaceEffectInput"
0x1801cdefa  mov     [rsp+40h+var_18], rax
0x1801cdeff  mov     r9d, esi
0x1801cdf02  mov     rdx, r14
0x1801cdf05  mov     [rsp+40h+var_20], rbx
0x1801cdf0a  mov     rcx, r15
0x1801cdf0d  mov     [rbp+arg_0], ebx
0x1801cdf10  call    cs:__imp_GetPersistedRegistryValueW
0x1801cdf16  test    eax, eax
0x1801cdf18  jnz     short loc_1801CDF28
0x1801cdf1a  cmp     [rbp+arg_0], ebx
0x1801cdf1d  mov     eax, ebx
0x1801cdf1f  setnz   al
0x1801cdf22  mov     cs:?m_fFlattenVirtualSurfaceBrush@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fFlattenVirtualSurfaceBrush
0x1801cdf28  mov     [rsp+40h+var_8], rbx
0x1801cdf2d  lea     rax, [rbp+arg_0]
0x1801cdf31  mov     [rsp+40h+var_10], edi
0x1801cdf35  lea     r8, aCpuclipflatten; "CpuClipFlatteningTolerance"
0x1801cdf3c  mov     [rsp+40h+var_18], rax
0x1801cdf41  mov     r9d, esi
0x1801cdf44  mov     rdx, r14
0x1801cdf47  mov     [rsp+40h+var_20], rbx
0x1801cdf4c  mov     rcx, r15
0x1801cdf4f  call    cs:__imp_GetPersistedRegistryValueW
0x1801cdf55  test    eax, eax
0x1801cdf57  jnz     short loc_1801CDF74
0x1801cdf59  mov     eax, [rbp+arg_0]
0x1801cdf5c  xorps   xmm0, xmm0
0x1801cdf5f  cvtsi2ss xmm0, rax
0x1801cdf64  divss   xmm0, cs:__real@447a0000
0x1801cdf6c  movss   cs:?m_flCpuClipFlatteningTolerance@CCommonRegistryData@@0MA, xmm0; float CCommonRegistryData::m_flCpuClipFlatteningTolerance
0x1801cdf74  mov     [rsp+40h+var_8], rbx
0x1801cdf79  lea     rax, [rbp+arg_0]
0x1801cdf7d  mov     [rsp+40h+var_10], edi
0x1801cdf81  lea     r8, aInteractionout; "InteractionOutputPredictionDisabled"
0x1801cdf88  mov     [rsp+40h+var_18], rax
0x1801cdf8d  mov     r9d, esi
0x1801cdf90  mov     rdx, r14
0x1801cdf93  mov     [rsp+40h+var_20], rbx
0x1801cdf98  mov     rcx, r15
0x1801cdf9b  call    cs:__imp_GetPersistedRegistryValueW
0x1801cdfa1  test    eax, eax
0x1801cdfa3  jnz     short loc_1801CDFB3
0x1801cdfa5  cmp     [rbp+arg_0], ebx
0x1801cdfa8  mov     eax, ebx
0x1801cdfaa  setnz   al
0x1801cdfad  mov     cs:?m_fDisableInteractionOutputPrediction@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDisableInteractionOutputPrediction
0x1801cdfb3  mov     [rsp+40h+var_8], rbx
0x1801cdfb8  lea     rax, [rbp+arg_0]
0x1801cdfbc  mov     [rsp+40h+var_10], edi
0x1801cdfc0  lea     r8, aBackdropblurca; "BackdropBlurCachingThrottleMs"
0x1801cdfc7  mov     [rsp+40h+var_18], rax
0x1801cdfcc  mov     r9d, esi
0x1801cdfcf  mov     rdx, r14
0x1801cdfd2  mov     [rsp+40h+var_20], rbx
0x1801cdfd7  mov     rcx, r15
0x1801cdfda  call    cs:__imp_GetPersistedRegistryValueW
0x1801cdfe0  test    eax, eax
0x1801cdfe2  jz      loc_1801CE354
0x1801cdfe8  imul    rcx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A, 19h; _LARGE_INTEGER g_qpcFrequency ...
0x1801cdff0  mov     [rsp+40h+var_8], rbx
0x1801cdff5  lea     r8, aForcenonprimar; "ForceNonPrimaryDisplayAdapter"
0x1801cdffc  mov     [rsp+40h+var_10], edi
0x1801ce000  mov     rax, 20C49BA5E353F7CFh
0x1801ce00a  imul    rcx
0x1801ce00d  mov     r9d, esi
0x1801ce010  mov     [rbp+arg_0], ebx
0x1801ce013  sar     rdx, 7
0x1801ce017  lea     rcx, aDwmsceneswitch; "DWMSceneSwitches"
0x1801ce01e  mov     rax, rdx
0x1801ce021  shr     rax, 3Fh
0x1801ce025  add     rdx, rax
0x1801ce028  lea     rax, [rbp+arg_0]
0x1801ce02c  mov     cs:?m_backdropBlurCachingThrottleQPCTimeDelta@CCommonRegistryData@@0_KA, rdx; unsigned __int64 CCommonRegistryData::m_backdropBlurCachingThrottleQPCTimeDelta
0x1801ce033  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Dwm\\Scen"...
0x1801ce03a  mov     [rsp+40h+var_18], rax
0x1801ce03f  mov     [rsp+40h+var_20], rbx
0x1801ce044  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce04a  test    eax, eax
0x1801ce04c  jnz     short loc_1801CE05C
0x1801ce04e  cmp     [rbp+arg_0], ebx
0x1801ce051  mov     eax, ebx
0x1801ce053  setnz   al
0x1801ce056  mov     cs:?m_fSceneForceNonPrimaryDisplayAdapter@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fSceneForceNonPrimaryDisplayAdapter
0x1801ce05c  mov     [rsp+40h+var_8], rbx
0x1801ce061  lea     rax, [rbp+arg_0]
0x1801ce065  mov     [rsp+40h+var_10], edi
0x1801ce069  lea     r8, aImageprocessin_2; "ImageProcessingResizeThreshold"
0x1801ce070  mov     [rsp+40h+var_18], rax
0x1801ce075  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Dwm\\Scen"...
0x1801ce07c  mov     r9d, esi
0x1801ce07f  mov     [rsp+40h+var_20], rbx
0x1801ce084  lea     rcx, aDwmsceneswitch; "DWMSceneSwitches"
0x1801ce08b  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce091  test    eax, eax
0x1801ce093  jnz     short loc_1801CE0B0
0x1801ce095  mov     eax, [rbp+arg_0]
0x1801ce098  xorps   xmm0, xmm0
0x1801ce09b  cvtsi2ss xmm0, rax
0x1801ce0a0  divss   xmm0, cs:__real@42c80000
0x1801ce0a8  movss   cs:?m_flSceneImageProcessingResizeThreshold@CCommonRegistryData@@0MA, xmm0; float CCommonRegistryData::m_flSceneImageProcessingResizeThreshold
0x1801ce0b0  mov     [rsp+40h+var_8], rbx
0x1801ce0b5  lea     rax, [rbp+arg_0]
0x1801ce0b9  mov     [rsp+40h+var_10], edi
0x1801ce0bd  lea     r8, aForceeffectmod; "ForceEffectMode"
0x1801ce0c4  mov     [rsp+40h+var_18], rax
0x1801ce0c9  mov     r9d, esi
0x1801ce0cc  mov     rdx, r14
0x1801ce0cf  mov     [rsp+40h+var_20], rbx
0x1801ce0d4  mov     rcx, r15
0x1801ce0d7  mov     [rbp+arg_0], ebx
0x1801ce0da  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce0e0  test    eax, eax
0x1801ce0e2  jz      loc_1801CE370
0x1801ce0e8  mov     [rsp+40h+var_8], rbx
0x1801ce0ed  lea     rax, [rbp+arg_0]
0x1801ce0f1  mov     [rsp+40h+var_10], edi
0x1801ce0f5  lea     r8, aCompositorcloc; "CompositorClockPolicy"
0x1801ce0fc  mov     r12d, 1
0x1801ce102  mov     [rsp+40h+var_18], rax
0x1801ce107  mov     r9d, esi
0x1801ce10a  mov     [rsp+40h+var_20], rbx
0x1801ce10f  mov     rdx, r14
0x1801ce112  mov     cs:?m_compositorClockPolicy@CCommonRegistryData@@0W4CompositorClockPolicy@@A, r12d; CompositorClockPolicy CCommonRegistryData::m_compositorClockPolicy
0x1801ce119  mov     rcx, r15
0x1801ce11c  mov     [rbp+arg_0], r12d
0x1801ce120  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce126  test    eax, eax
0x1801ce128  jz      loc_1801CE387
0x1801ce12e  mov     [rsp+40h+var_8], rbx
0x1801ce133  lea     rax, [rbp+arg_0]
0x1801ce137  mov     [rsp+40h+var_10], edi
0x1801ce13b  lea     r8, aParallelmodepo; "ParallelModePolicy"
0x1801ce142  mov     [rsp+40h+var_18], rax
0x1801ce147  mov     r9d, esi
0x1801ce14a  mov     rdx, r14
0x1801ce14d  mov     [rsp+40h+var_20], rbx
0x1801ce152  mov     rcx, r15
0x1801ce155  mov     [rbp+arg_0], r12d
0x1801ce159  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce15f  test    eax, eax
0x1801ce161  jz      loc_1801CE39E
0x1801ce167  mov     [rsp+40h+var_8], rbx
0x1801ce16c  lea     rax, [rbp+arg_0]
0x1801ce170  mov     [rsp+40h+var_10], edi
0x1801ce174  lea     r8, aParallelmodera; "ParallelModeRateThreshold"
0x1801ce17b  mov     [rsp+40h+var_18], rax
0x1801ce180  mov     r9d, esi
0x1801ce183  mov     rdx, r14
0x1801ce186  mov     [rsp+40h+var_20], rbx
0x1801ce18b  mov     rcx, r15
0x1801ce18e  mov     [rbp+arg_0], r12d
0x1801ce192  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce198  test    eax, eax
0x1801ce19a  jz      loc_1801CE3B2
0x1801ce1a0  mov     rax, 89AE4089AE4089AFh
0x1801ce1aa  imul    qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x1801ce1b1  add     rdx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x1801ce1b8  sar     rdx, 6
0x1801ce1bc  mov     rax, rdx
0x1801ce1bf  shr     rax, 3Fh
0x1801ce1c3  add     rdx, rax
0x1801ce1c6  mov     [rsp+40h+var_8], rbx
0x1801ce1cb  lea     rax, [rbp+arg_0]
0x1801ce1cf  mov     [rsp+40h+var_10], edi
0x1801ce1d3  lea     r8, aCustomrefreshr; "CustomRefreshRateMode"
0x1801ce1da  mov     cs:?m_parallelModeDurationThreshold@CCommonRegistryData@@0_KA, rdx; unsigned __int64 CCommonRegistryData::m_parallelModeDurationThreshold
0x1801ce1e1  mov     r9d, esi
0x1801ce1e4  mov     [rsp+40h+var_18], rax
0x1801ce1e9  mov     rdx, r14
0x1801ce1ec  mov     rcx, r15
0x1801ce1ef  mov     [rsp+40h+var_20], rbx
0x1801ce1f4  mov     [rbp+arg_0], ebx
0x1801ce1f7  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce1fd  test    eax, eax
0x1801ce1ff  jz      loc_1801CE3C5
0x1801ce205  mov     [rsp+40h+var_8], rbx
0x1801ce20a  lea     rax, [rbp+arg_0]
0x1801ce20e  mov     [rsp+40h+var_10], edi
0x1801ce212  lea     r8, aSdrboostpercen; "SDRBoostPercentOverride"
0x1801ce219  mov     [rsp+40h+var_18], rax
0x1801ce21e  mov     r9d, esi
0x1801ce221  mov     rdx, r14
0x1801ce224  mov     [rsp+40h+var_20], rbx
0x1801ce229  mov     rcx, r15
0x1801ce22c  mov     [rbp+arg_0], ebx
0x1801ce22f  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce235  test    eax, eax
0x1801ce237  jnz     short loc_1801CE254
0x1801ce239  mov     eax, [rbp+arg_0]
0x1801ce23c  xorps   xmm0, xmm0
0x1801ce23f  cvtsi2ss xmm0, rax
0x1801ce244  divss   xmm0, cs:__real@42c80000
0x1801ce24c  movss   cs:?m_flSDRBoostOverride@CCommonRegistryData@@0MA, xmm0; float CCommonRegistryData::m_flSDRBoostOverride
0x1801ce254  mov     [rsp+40h+var_8], rbx
0x1801ce259  lea     rax, [rbp+arg_0]
0x1801ce25d  mov     [rsp+40h+var_10], edi
0x1801ce261  lea     r8, aDisableproject_0; "DisableProjectedShadowsRendering"
0x1801ce268  mov     [rsp+40h+var_18], rax
0x1801ce26d  mov     r9d, esi
0x1801ce270  mov     rdx, r14
0x1801ce273  mov     [rsp+40h+var_20], rbx
0x1801ce278  mov     rcx, r15
0x1801ce27b  mov     [rbp+arg_0], ebx
0x1801ce27e  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce284  mov     [rsp+40h+var_8], rbx
0x1801ce289  lea     rax, [rbp+arg_0]
0x1801ce28d  mov     [rsp+40h+var_10], edi
0x1801ce291  lea     r8, aShowdirtyregio; "ShowDirtyRegions"
0x1801ce298  mov     [rsp+40h+var_18], rax
0x1801ce29d  mov     r9d, esi
0x1801ce2a0  mov     rdx, r14
0x1801ce2a3  mov     [rsp+40h+var_20], rbx
0x1801ce2a8  mov     rcx, r15
0x1801ce2ab  mov     [rbp+arg_0], ebx
0x1801ce2ae  call    cs:__imp_GetPersistedRegistryValueW
0x1801ce2b4  test    eax, eax
0x1801ce2b6  jnz     short loc_1801CE2C1
0x1801ce2b8  mov     eax, [rbp+arg_0]
0x1801ce2bb  mov     cs:?m_fShowDirtyRegions@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fShowDirtyRegions
0x1801ce2c1  mov     [rsp+40h+var_8], rbx
0x1801ce2c6  lea     rax, [rbp+arg_0]
  ... truncated ...
```
