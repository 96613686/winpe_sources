# wil_InitializeFeatureStaging

- ea: `0x14002e8a0`
- end: `0x14002e957`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002e078`

## callees

- `0x140003c24`
- `0x1400185dc`
- `0x14001887c`
- `0x14002e8a0`
- `0x14002e960`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002e91e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002e91e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002e8c8`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002e8c8`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  __int64 *i; // rcx
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
  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v2 + 56) )
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
0x14002e8a0  push    rbx
0x14002e8a2  sub     rsp, 20h
0x14002e8a6  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002e8ad  mov     [rsp+28h+arg_0], 0
0x14002e8b6  jnz     loc_14002E94E
0x14002e8bc  xor     ebx, ebx
0x14002e8be  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14002e8c8  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14002e8cf  nop     dword ptr [rax+rax+00h]
0x14002e8d4  mov     [rsp+28h+arg_0], rax
0x14002e8d9  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14002e8de  call    wil_details_EvaluateFeatureDependencies
0x14002e8e3  lea     rcx, wil_details_featureDescriptors_a
0x14002e8ea  call    wil_details_FeatureDescriptors_SkipPadding
0x14002e8ef  test    rax, rax
0x14002e8f2  jz      short loc_14002E93C
0x14002e8f4  cmp     [rax+1Dh], bl
0x14002e8f7  jnz     short loc_14002E903
0x14002e8f9  cmp     [rax+1Eh], bl
0x14002e8fc  jnz     short loc_14002E903
0x14002e8fe  cmp     [rax+1Ch], bl
0x14002e901  jz      short loc_14002E909
0x14002e903  lea     rcx, [rax+38h]
0x14002e907  jmp     short loc_14002E8EA
0x14002e909  lea     r9, g_wil_details_featureChangeNotification
0x14002e910  xor     edx, edx
0x14002e912  lea     r8, [rsp+28h+arg_0]
0x14002e917  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14002e91e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14002e925  nop     dword ptr [rax+rax+00h]
0x14002e92a  test    eax, eax
0x14002e92c  jz      short loc_14002E937
0x14002e92e  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14002e935  jmp     short loc_14002E93C
0x14002e937  mov     ebx, 1
0x14002e93c  call    wil_details_RegisterFeatureUsageProvider
0x14002e941  test    eax, eax
0x14002e943  jz      short loc_14002E94E
0x14002e945  xor     ecx, ecx
0x14002e947  test    ebx, ebx
0x14002e949  cmovnz  eax, ecx
0x14002e94c  jmp     short loc_14002E950
0x14002e94e  xor     eax, eax
0x14002e950  add     rsp, 20h
0x14002e954  pop     rbx
0x14002e955  retn
```
