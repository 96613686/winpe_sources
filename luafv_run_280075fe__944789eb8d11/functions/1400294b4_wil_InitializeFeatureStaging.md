# wil_InitializeFeatureStaging

- ea: `0x1400294b4`
- end: `0x14002956b`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400291a8`

## callees

- `0x1400031ac`
- `0x14001692c`
- `0x140016bcc`
- `0x1400294b4`
- `0x140029574`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400294dc`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400294dc`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140029532`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140029532`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  __int64 **i; // rcx
  _BYTE *v2; // rax
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  v0 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 **)(v2 + 56) )
  {
    v2 = (_BYTE *)wil_details_FeatureDescriptors_SkipPadding(i);
    if ( !v2 )
      break;
    if ( !v2[29] && !v2[30] && !v2[28] )
    {
      if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                           wil_details_ReevaluateOnFeatureConfigurationChange,
                           0,
                           &v4,
                           &g_wil_details_featureChangeNotification) )
        g_wil_details_featureChangeNotification = 0;
      else
        v0 = 1;
      break;
    }
  }
  result = wil_details_RegisterFeatureUsageProvider();
  if ( !(_DWORD)result )
    return 0;
  if ( v0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1400294b4  push    rbx
0x1400294b6  sub     rsp, 20h
0x1400294ba  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400294c1  mov     [rsp+28h+arg_0], 0
0x1400294ca  jnz     loc_140029562
0x1400294d0  xor     ebx, ebx
0x1400294d2  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400294dc  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400294e3  nop     dword ptr [rax+rax+00h]
0x1400294e8  mov     [rsp+28h+arg_0], rax
0x1400294ed  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400294f2  call    wil_details_EvaluateFeatureDependencies
0x1400294f7  lea     rcx, wil_details_featureDescriptors_a
0x1400294fe  call    wil_details_FeatureDescriptors_SkipPadding
0x140029503  test    rax, rax
0x140029506  jz      short loc_140029550
0x140029508  cmp     [rax+1Dh], bl
0x14002950b  jnz     short loc_140029517
0x14002950d  cmp     [rax+1Eh], bl
0x140029510  jnz     short loc_140029517
0x140029512  cmp     [rax+1Ch], bl
0x140029515  jz      short loc_14002951D
0x140029517  lea     rcx, [rax+38h]
0x14002951b  jmp     short loc_1400294FE
0x14002951d  lea     r9, g_wil_details_featureChangeNotification
0x140029524  xor     edx, edx
0x140029526  lea     r8, [rsp+28h+arg_0]
0x14002952b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140029532  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140029539  nop     dword ptr [rax+rax+00h]
0x14002953e  test    eax, eax
0x140029540  jz      short loc_14002954B
0x140029542  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140029549  jmp     short loc_140029550
0x14002954b  mov     ebx, 1
0x140029550  call    wil_details_RegisterFeatureUsageProvider
0x140029555  test    eax, eax
0x140029557  jz      short loc_140029562
0x140029559  xor     ecx, ecx
0x14002955b  test    ebx, ebx
0x14002955d  cmovnz  eax, ecx
0x140029560  jmp     short loc_140029564
0x140029562  xor     eax, eax
0x140029564  add     rsp, 20h
0x140029568  pop     rbx
0x140029569  retn
```
