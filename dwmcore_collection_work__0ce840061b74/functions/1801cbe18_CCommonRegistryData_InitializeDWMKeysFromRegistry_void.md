# CCommonRegistryData::InitializeDWMKeysFromRegistry(void)

- ea: `0x1801cbe18`
- end: `0x1801cc42c`
- name: `?InitializeDWMKeysFromRegistry@CCommonRegistryData@@CAXXZ`
- size: `1556`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801cbd60`

## callees

- `0x1801cbe18`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbe6f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbeac`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbedc`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbf1e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbf60`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbf9f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbfeb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc02a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc094`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc0db`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc12a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc170`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc1a9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc1e2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc247`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc27f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc2ce`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc2fe`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc33b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc378`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbe6f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbeac`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbedc`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbf1e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbf60`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbf9f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cbfeb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc02a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc094`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc0db`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc12a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc170`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc1a9`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc1e2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc247`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc27f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc2ce`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc2fe`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc33b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x1801cc378`

## string_xrefs

- `0x1801cc145`: `CompositorClockPolicy`

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
0x1801cbe18  mov     r11, rsp
0x1801cbe1b  mov     [r11+10h], rbx
0x1801cbe1f  mov     [r11+18h], rsi
0x1801cbe23  push    rbp
0x1801cbe24  push    rdi
0x1801cbe25  push    r12
0x1801cbe27  push    r14
0x1801cbe29  push    r15
0x1801cbe2b  mov     rbp, rsp
0x1801cbe2e  sub     rsp, 40h
0x1801cbe32  xor     ebx, ebx
0x1801cbe34  lea     rax, [rbp+arg_0]
0x1801cbe38  mov     [r11-30h], rbx
0x1801cbe3c  lea     r14, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Dwm"
0x1801cbe43  lea     r15, aDwmswitches; "DWMSwitches"
0x1801cbe4a  mov     [rbp+arg_0], ebx
0x1801cbe4d  lea     r8, aOverlaytestmod; "OverlayTestMode"
0x1801cbe54  mov     rdx, r14
0x1801cbe57  lea     edi, [rbx+4]
0x1801cbe5a  mov     rcx, r15
0x1801cbe5d  mov     [rsp+40h+var_10], edi
0x1801cbe61  lea     esi, [rbx+10h]
0x1801cbe64  mov     [r11-40h], rax
0x1801cbe68  mov     r9d, esi
0x1801cbe6b  mov     [r11-48h], rbx
0x1801cbe6f  call    cs:__imp_GetPersistedRegistryValueW
0x1801cbe75  test    eax, eax
0x1801cbe77  jnz     short loc_1801CBE82
0x1801cbe79  mov     eax, [rbp+arg_0]
0x1801cbe7c  mov     cs:?m_dwOverlayTestMode@CCommonRegistryData@@0KA, eax; ulong CCommonRegistryData::m_dwOverlayTestMode
0x1801cbe82  mov     [rsp+40h+var_8], rbx
0x1801cbe87  lea     rax, [rbp+arg_0]
0x1801cbe8b  mov     [rsp+40h+var_10], edi
0x1801cbe8f  lea     r8, aDisableadvance; "DisableAdvancedDirectFlip"
0x1801cbe96  mov     [rsp+40h+var_18], rax
0x1801cbe9b  mov     r9d, esi
0x1801cbe9e  mov     rdx, r14
0x1801cbea1  mov     [rsp+40h+var_20], rbx
0x1801cbea6  mov     rcx, r15
0x1801cbea9  mov     [rbp+arg_0], ebx
0x1801cbeac  call    cs:__imp_GetPersistedRegistryValueW
0x1801cbeb2  mov     [rsp+40h+var_8], rbx
0x1801cbeb7  lea     rax, [rbp+arg_0]
0x1801cbebb  mov     [rsp+40h+var_10], edi
0x1801cbebf  lea     r8, aDisableindepen; "DisableIndependentFlip"
0x1801cbec6  mov     [rsp+40h+var_18], rax
0x1801cbecb  mov     r9d, esi
0x1801cbece  mov     rdx, r14
0x1801cbed1  mov     [rsp+40h+var_20], rbx
0x1801cbed6  mov     rcx, r15
0x1801cbed9  mov     [rbp+arg_0], ebx
0x1801cbedc  call    cs:__imp_GetPersistedRegistryValueW
0x1801cbee2  test    eax, eax
0x1801cbee4  jnz     short loc_1801CBEF4
0x1801cbee6  cmp     [rbp+arg_0], ebx
0x1801cbee9  mov     eax, ebx
0x1801cbeeb  setnz   al
0x1801cbeee  mov     cs:?m_fDisableIndependentFlip@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDisableIndependentFlip
0x1801cbef4  mov     [rsp+40h+var_8], rbx
0x1801cbef9  lea     rax, [rbp+arg_0]
0x1801cbefd  mov     [rsp+40h+var_10], edi
0x1801cbf01  lea     r8, aFramecounterpo; "FrameCounterPosition"
0x1801cbf08  mov     [rsp+40h+var_18], rax
0x1801cbf0d  mov     r9d, esi
0x1801cbf10  mov     rdx, r14
0x1801cbf13  mov     [rsp+40h+var_20], rbx
0x1801cbf18  mov     rcx, r15
0x1801cbf1b  mov     [rbp+arg_0], ebx
0x1801cbf1e  call    cs:__imp_GetPersistedRegistryValueW
0x1801cbf24  test    eax, eax
0x1801cbf26  jnz     short loc_1801CBF36
0x1801cbf28  cmp     [rbp+arg_0], ebx
0x1801cbf2b  mov     eax, ebx
0x1801cbf2d  setnz   al
0x1801cbf30  mov     cs:?m_fDebugFrameCounterIsVertical@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDebugFrameCounterIsVertical
0x1801cbf36  mov     [rsp+40h+var_8], rbx
0x1801cbf3b  lea     rax, [rbp+arg_0]
0x1801cbf3f  mov     [rsp+40h+var_10], edi
0x1801cbf43  lea     r8, aFlattenvirtual; "FlattenVirtualSurfaceEffectInput"
0x1801cbf4a  mov     [rsp+40h+var_18], rax
0x1801cbf4f  mov     r9d, esi
0x1801cbf52  mov     rdx, r14
0x1801cbf55  mov     [rsp+40h+var_20], rbx
0x1801cbf5a  mov     rcx, r15
0x1801cbf5d  mov     [rbp+arg_0], ebx
0x1801cbf60  call    cs:__imp_GetPersistedRegistryValueW
0x1801cbf66  test    eax, eax
0x1801cbf68  jnz     short loc_1801CBF78
0x1801cbf6a  cmp     [rbp+arg_0], ebx
0x1801cbf6d  mov     eax, ebx
0x1801cbf6f  setnz   al
0x1801cbf72  mov     cs:?m_fFlattenVirtualSurfaceBrush@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fFlattenVirtualSurfaceBrush
0x1801cbf78  mov     [rsp+40h+var_8], rbx
0x1801cbf7d  lea     rax, [rbp+arg_0]
0x1801cbf81  mov     [rsp+40h+var_10], edi
0x1801cbf85  lea     r8, aCpuclipflatten; "CpuClipFlatteningTolerance"
0x1801cbf8c  mov     [rsp+40h+var_18], rax
0x1801cbf91  mov     r9d, esi
0x1801cbf94  mov     rdx, r14
0x1801cbf97  mov     [rsp+40h+var_20], rbx
0x1801cbf9c  mov     rcx, r15
0x1801cbf9f  call    cs:__imp_GetPersistedRegistryValueW
0x1801cbfa5  test    eax, eax
0x1801cbfa7  jnz     short loc_1801CBFC4
0x1801cbfa9  mov     eax, [rbp+arg_0]
0x1801cbfac  xorps   xmm0, xmm0
0x1801cbfaf  cvtsi2ss xmm0, rax
0x1801cbfb4  divss   xmm0, cs:__real@447a0000
0x1801cbfbc  movss   cs:?m_flCpuClipFlatteningTolerance@CCommonRegistryData@@0MA, xmm0; float CCommonRegistryData::m_flCpuClipFlatteningTolerance
0x1801cbfc4  mov     [rsp+40h+var_8], rbx
0x1801cbfc9  lea     rax, [rbp+arg_0]
0x1801cbfcd  mov     [rsp+40h+var_10], edi
0x1801cbfd1  lea     r8, aInteractionout; "InteractionOutputPredictionDisabled"
0x1801cbfd8  mov     [rsp+40h+var_18], rax
0x1801cbfdd  mov     r9d, esi
0x1801cbfe0  mov     rdx, r14
0x1801cbfe3  mov     [rsp+40h+var_20], rbx
0x1801cbfe8  mov     rcx, r15
0x1801cbfeb  call    cs:__imp_GetPersistedRegistryValueW
0x1801cbff1  test    eax, eax
0x1801cbff3  jnz     short loc_1801CC003
0x1801cbff5  cmp     [rbp+arg_0], ebx
0x1801cbff8  mov     eax, ebx
0x1801cbffa  setnz   al
0x1801cbffd  mov     cs:?m_fDisableInteractionOutputPrediction@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDisableInteractionOutputPrediction
0x1801cc003  mov     [rsp+40h+var_8], rbx
0x1801cc008  lea     rax, [rbp+arg_0]
0x1801cc00c  mov     [rsp+40h+var_10], edi
0x1801cc010  lea     r8, aBackdropblurca; "BackdropBlurCachingThrottleMs"
0x1801cc017  mov     [rsp+40h+var_18], rax
0x1801cc01c  mov     r9d, esi
0x1801cc01f  mov     rdx, r14
0x1801cc022  mov     [rsp+40h+var_20], rbx
0x1801cc027  mov     rcx, r15
0x1801cc02a  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc030  test    eax, eax
0x1801cc032  jz      loc_1801CC3A4
0x1801cc038  imul    rcx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A, 19h; _LARGE_INTEGER g_qpcFrequency ...
0x1801cc040  mov     [rsp+40h+var_8], rbx
0x1801cc045  lea     r8, aForcenonprimar; "ForceNonPrimaryDisplayAdapter"
0x1801cc04c  mov     [rsp+40h+var_10], edi
0x1801cc050  mov     rax, 20C49BA5E353F7CFh
0x1801cc05a  imul    rcx
0x1801cc05d  mov     r9d, esi
0x1801cc060  mov     [rbp+arg_0], ebx
0x1801cc063  sar     rdx, 7
0x1801cc067  lea     rcx, aDwmsceneswitch; "DWMSceneSwitches"
0x1801cc06e  mov     rax, rdx
0x1801cc071  shr     rax, 3Fh
0x1801cc075  add     rdx, rax
0x1801cc078  lea     rax, [rbp+arg_0]
0x1801cc07c  mov     cs:?m_backdropBlurCachingThrottleQPCTimeDelta@CCommonRegistryData@@0_KA, rdx; unsigned __int64 CCommonRegistryData::m_backdropBlurCachingThrottleQPCTimeDelta
0x1801cc083  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Dwm\\Scen"...
0x1801cc08a  mov     [rsp+40h+var_18], rax
0x1801cc08f  mov     [rsp+40h+var_20], rbx
0x1801cc094  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc09a  test    eax, eax
0x1801cc09c  jnz     short loc_1801CC0AC
0x1801cc09e  cmp     [rbp+arg_0], ebx
0x1801cc0a1  mov     eax, ebx
0x1801cc0a3  setnz   al
0x1801cc0a6  mov     cs:?m_fSceneForceNonPrimaryDisplayAdapter@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fSceneForceNonPrimaryDisplayAdapter
0x1801cc0ac  mov     [rsp+40h+var_8], rbx
0x1801cc0b1  lea     rax, [rbp+arg_0]
0x1801cc0b5  mov     [rsp+40h+var_10], edi
0x1801cc0b9  lea     r8, aImageprocessin_2; "ImageProcessingResizeThreshold"
0x1801cc0c0  mov     [rsp+40h+var_18], rax
0x1801cc0c5  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Dwm\\Scen"...
0x1801cc0cc  mov     r9d, esi
0x1801cc0cf  mov     [rsp+40h+var_20], rbx
0x1801cc0d4  lea     rcx, aDwmsceneswitch; "DWMSceneSwitches"
0x1801cc0db  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc0e1  test    eax, eax
0x1801cc0e3  jnz     short loc_1801CC100
0x1801cc0e5  mov     eax, [rbp+arg_0]
0x1801cc0e8  xorps   xmm0, xmm0
0x1801cc0eb  cvtsi2ss xmm0, rax
0x1801cc0f0  divss   xmm0, cs:__real@42c80000
0x1801cc0f8  movss   cs:?m_flSceneImageProcessingResizeThreshold@CCommonRegistryData@@0MA, xmm0; float CCommonRegistryData::m_flSceneImageProcessingResizeThreshold
0x1801cc100  mov     [rsp+40h+var_8], rbx
0x1801cc105  lea     rax, [rbp+arg_0]
0x1801cc109  mov     [rsp+40h+var_10], edi
0x1801cc10d  lea     r8, aForceeffectmod; "ForceEffectMode"
0x1801cc114  mov     [rsp+40h+var_18], rax
0x1801cc119  mov     r9d, esi
0x1801cc11c  mov     rdx, r14
0x1801cc11f  mov     [rsp+40h+var_20], rbx
0x1801cc124  mov     rcx, r15
0x1801cc127  mov     [rbp+arg_0], ebx
0x1801cc12a  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc130  test    eax, eax
0x1801cc132  jz      loc_1801CC3C0
0x1801cc138  mov     [rsp+40h+var_8], rbx
0x1801cc13d  lea     rax, [rbp+arg_0]
0x1801cc141  mov     [rsp+40h+var_10], edi
0x1801cc145  lea     r8, aCompositorcloc; "CompositorClockPolicy"
0x1801cc14c  mov     r12d, 1
0x1801cc152  mov     [rsp+40h+var_18], rax
0x1801cc157  mov     r9d, esi
0x1801cc15a  mov     [rsp+40h+var_20], rbx
0x1801cc15f  mov     rdx, r14
0x1801cc162  mov     cs:?m_compositorClockPolicy@CCommonRegistryData@@0W4CompositorClockPolicy@@A, r12d; CompositorClockPolicy CCommonRegistryData::m_compositorClockPolicy
0x1801cc169  mov     rcx, r15
0x1801cc16c  mov     [rbp+arg_0], r12d
0x1801cc170  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc176  test    eax, eax
0x1801cc178  jz      loc_1801CC3D7
0x1801cc17e  mov     [rsp+40h+var_8], rbx
0x1801cc183  lea     rax, [rbp+arg_0]
0x1801cc187  mov     [rsp+40h+var_10], edi
0x1801cc18b  lea     r8, aParallelmodepo; "ParallelModePolicy"
0x1801cc192  mov     [rsp+40h+var_18], rax
0x1801cc197  mov     r9d, esi
0x1801cc19a  mov     rdx, r14
0x1801cc19d  mov     [rsp+40h+var_20], rbx
0x1801cc1a2  mov     rcx, r15
0x1801cc1a5  mov     [rbp+arg_0], r12d
0x1801cc1a9  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc1af  test    eax, eax
0x1801cc1b1  jz      loc_1801CC3EE
0x1801cc1b7  mov     [rsp+40h+var_8], rbx
0x1801cc1bc  lea     rax, [rbp+arg_0]
0x1801cc1c0  mov     [rsp+40h+var_10], edi
0x1801cc1c4  lea     r8, aParallelmodera; "ParallelModeRateThreshold"
0x1801cc1cb  mov     [rsp+40h+var_18], rax
0x1801cc1d0  mov     r9d, esi
0x1801cc1d3  mov     rdx, r14
0x1801cc1d6  mov     [rsp+40h+var_20], rbx
0x1801cc1db  mov     rcx, r15
0x1801cc1de  mov     [rbp+arg_0], r12d
0x1801cc1e2  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc1e8  test    eax, eax
0x1801cc1ea  jz      loc_1801CC402
0x1801cc1f0  mov     rax, 89AE4089AE4089AFh
0x1801cc1fa  imul    qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x1801cc201  add     rdx, qword ptr cs:?g_qpcFrequency@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_qpcFrequency ...
0x1801cc208  sar     rdx, 6
0x1801cc20c  mov     rax, rdx
0x1801cc20f  shr     rax, 3Fh
0x1801cc213  add     rdx, rax
0x1801cc216  mov     [rsp+40h+var_8], rbx
0x1801cc21b  lea     rax, [rbp+arg_0]
0x1801cc21f  mov     [rsp+40h+var_10], edi
0x1801cc223  lea     r8, aCustomrefreshr; "CustomRefreshRateMode"
0x1801cc22a  mov     cs:?m_parallelModeDurationThreshold@CCommonRegistryData@@0_KA, rdx; unsigned __int64 CCommonRegistryData::m_parallelModeDurationThreshold
0x1801cc231  mov     r9d, esi
0x1801cc234  mov     [rsp+40h+var_18], rax
0x1801cc239  mov     rdx, r14
0x1801cc23c  mov     rcx, r15
0x1801cc23f  mov     [rsp+40h+var_20], rbx
0x1801cc244  mov     [rbp+arg_0], ebx
0x1801cc247  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc24d  test    eax, eax
0x1801cc24f  jz      loc_1801CC415
0x1801cc255  mov     [rsp+40h+var_8], rbx
0x1801cc25a  lea     rax, [rbp+arg_0]
0x1801cc25e  mov     [rsp+40h+var_10], edi
0x1801cc262  lea     r8, aSdrboostpercen; "SDRBoostPercentOverride"
0x1801cc269  mov     [rsp+40h+var_18], rax
0x1801cc26e  mov     r9d, esi
0x1801cc271  mov     rdx, r14
0x1801cc274  mov     [rsp+40h+var_20], rbx
0x1801cc279  mov     rcx, r15
0x1801cc27c  mov     [rbp+arg_0], ebx
0x1801cc27f  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc285  test    eax, eax
0x1801cc287  jnz     short loc_1801CC2A4
0x1801cc289  mov     eax, [rbp+arg_0]
0x1801cc28c  xorps   xmm0, xmm0
0x1801cc28f  cvtsi2ss xmm0, rax
0x1801cc294  divss   xmm0, cs:__real@42c80000
0x1801cc29c  movss   cs:?m_flSDRBoostOverride@CCommonRegistryData@@0MA, xmm0; float CCommonRegistryData::m_flSDRBoostOverride
0x1801cc2a4  mov     [rsp+40h+var_8], rbx
0x1801cc2a9  lea     rax, [rbp+arg_0]
0x1801cc2ad  mov     [rsp+40h+var_10], edi
0x1801cc2b1  lea     r8, aDisableproject_0; "DisableProjectedShadowsRendering"
0x1801cc2b8  mov     [rsp+40h+var_18], rax
0x1801cc2bd  mov     r9d, esi
0x1801cc2c0  mov     rdx, r14
0x1801cc2c3  mov     [rsp+40h+var_20], rbx
0x1801cc2c8  mov     rcx, r15
0x1801cc2cb  mov     [rbp+arg_0], ebx
0x1801cc2ce  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc2d4  mov     [rsp+40h+var_8], rbx
0x1801cc2d9  lea     rax, [rbp+arg_0]
0x1801cc2dd  mov     [rsp+40h+var_10], edi
0x1801cc2e1  lea     r8, aShowdirtyregio; "ShowDirtyRegions"
0x1801cc2e8  mov     [rsp+40h+var_18], rax
0x1801cc2ed  mov     r9d, esi
0x1801cc2f0  mov     rdx, r14
0x1801cc2f3  mov     [rsp+40h+var_20], rbx
0x1801cc2f8  mov     rcx, r15
0x1801cc2fb  mov     [rbp+arg_0], ebx
0x1801cc2fe  call    cs:__imp_GetPersistedRegistryValueW
0x1801cc304  test    eax, eax
0x1801cc306  jnz     short loc_1801CC311
0x1801cc308  mov     eax, [rbp+arg_0]
0x1801cc30b  mov     cs:?m_fShowDirtyRegions@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fShowDirtyRegions
0x1801cc311  mov     [rsp+40h+var_8], rbx
0x1801cc316  lea     rax, [rbp+arg_0]
  ... truncated ...
```
