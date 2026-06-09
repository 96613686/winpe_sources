# wil_InitializeFeatureStaging

- ea: `0x1400472ec`
- end: `0x1400473a3`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140047080`

## callees

- `0x140029f9c`
- `0x140043168`
- `0x1400433fc`
- `0x1400472ec`
- `0x1400473ac`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140047314`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140047314`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14004736a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14004736a`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  int **i; // rcx
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
  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v2 + 56) )
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
0x1400472ec  push    rbx
0x1400472ee  sub     rsp, 20h
0x1400472f2  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400472f9  mov     [rsp+28h+arg_0], 0
0x140047302  jnz     loc_14004739A
0x140047308  xor     ebx, ebx
0x14004730a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140047314  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14004731b  nop     dword ptr [rax+rax+00h]
0x140047320  mov     [rsp+28h+arg_0], rax
0x140047325  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14004732a  call    wil_details_EvaluateFeatureDependencies
0x14004732f  lea     rcx, wil_details_featureDescriptors_a
0x140047336  call    wil_details_FeatureDescriptors_SkipPadding
0x14004733b  test    rax, rax
0x14004733e  jz      short loc_140047388
0x140047340  cmp     [rax+1Dh], bl
0x140047343  jnz     short loc_14004734F
0x140047345  cmp     [rax+1Eh], bl
0x140047348  jnz     short loc_14004734F
0x14004734a  cmp     [rax+1Ch], bl
0x14004734d  jz      short loc_140047355
0x14004734f  lea     rcx, [rax+38h]
0x140047353  jmp     short loc_140047336
0x140047355  lea     r9, g_wil_details_featureChangeNotification
0x14004735c  xor     edx, edx
0x14004735e  lea     r8, [rsp+28h+arg_0]
0x140047363  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14004736a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140047371  nop     dword ptr [rax+rax+00h]
0x140047376  test    eax, eax
0x140047378  jz      short loc_140047383
0x14004737a  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140047381  jmp     short loc_140047388
0x140047383  mov     ebx, 1
0x140047388  call    wil_details_RegisterFeatureUsageProvider
0x14004738d  test    eax, eax
0x14004738f  jz      short loc_14004739A
0x140047391  xor     ecx, ecx
0x140047393  test    ebx, ebx
0x140047395  cmovnz  eax, ecx
0x140047398  jmp     short loc_14004739C
0x14004739a  xor     eax, eax
0x14004739c  add     rsp, 20h
0x1400473a0  pop     rbx
0x1400473a1  retn
```
