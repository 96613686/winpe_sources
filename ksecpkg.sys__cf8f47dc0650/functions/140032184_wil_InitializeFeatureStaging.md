# wil_InitializeFeatureStaging

- ea: `0x140032184`
- end: `0x14003223b`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140032078`

## callees

- `0x140007124`
- `0x14002031c`
- `0x1400205bc`
- `0x140032184`
- `0x140032244`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140032202`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140032202`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400321ac`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400321ac`

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
  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v2 + 56) )
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
0x140032184  push    rbx
0x140032186  sub     rsp, 20h
0x14003218a  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140032191  mov     [rsp+28h+arg_0], 0
0x14003219a  jnz     loc_140032232
0x1400321a0  xor     ebx, ebx
0x1400321a2  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400321ac  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400321b3  nop     dword ptr [rax+rax+00h]
0x1400321b8  mov     [rsp+28h+arg_0], rax
0x1400321bd  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400321c2  call    wil_details_EvaluateFeatureDependencies
0x1400321c7  lea     rcx, wil_details_featureDescriptors_a
0x1400321ce  call    wil_details_FeatureDescriptors_SkipPadding
0x1400321d3  test    rax, rax
0x1400321d6  jz      short loc_140032220
0x1400321d8  cmp     [rax+1Dh], bl
0x1400321db  jnz     short loc_1400321E7
0x1400321dd  cmp     [rax+1Eh], bl
0x1400321e0  jnz     short loc_1400321E7
0x1400321e2  cmp     [rax+1Ch], bl
0x1400321e5  jz      short loc_1400321ED
0x1400321e7  lea     rcx, [rax+38h]
0x1400321eb  jmp     short loc_1400321CE
0x1400321ed  lea     r9, g_wil_details_featureChangeNotification
0x1400321f4  xor     edx, edx
0x1400321f6  lea     r8, [rsp+28h+arg_0]
0x1400321fb  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140032202  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140032209  nop     dword ptr [rax+rax+00h]
0x14003220e  test    eax, eax
0x140032210  jz      short loc_14003221B
0x140032212  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140032219  jmp     short loc_140032220
0x14003221b  mov     ebx, 1
0x140032220  call    wil_details_RegisterFeatureUsageProvider
0x140032225  test    eax, eax
0x140032227  jz      short loc_140032232
0x140032229  xor     ecx, ecx
0x14003222b  test    ebx, ebx
0x14003222d  cmovnz  eax, ecx
0x140032230  jmp     short loc_140032234
0x140032232  xor     eax, eax
0x140032234  add     rsp, 20h
0x140032238  pop     rbx
0x140032239  retn
```
