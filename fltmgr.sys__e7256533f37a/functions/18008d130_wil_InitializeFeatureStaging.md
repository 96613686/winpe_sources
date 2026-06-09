# wil_InitializeFeatureStaging

- ea: `0x18008d130`
- end: `0x18008d1e7`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18008c078`

## callees

- `0x18001dd20`
- `0x180051c28`
- `0x180076610`
- `0x18008d130`
- `0x18008d1f0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18008d1ae`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18008d1ae`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18008d158`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18008d158`

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
0x18008d130  push    rbx
0x18008d132  sub     rsp, 20h
0x18008d136  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x18008d13d  mov     [rsp+28h+arg_0], 0
0x18008d146  jnz     loc_18008D1DE
0x18008d14c  xor     ebx, ebx
0x18008d14e  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x18008d158  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x18008d15f  nop     dword ptr [rax+rax+00h]
0x18008d164  mov     [rsp+28h+arg_0], rax
0x18008d169  call    wil_details_PopulateInitialConfiguredFeatureStates
0x18008d16e  call    wil_details_EvaluateFeatureDependencies
0x18008d173  lea     rcx, wil_details_featureDescriptors_a
0x18008d17a  call    wil_details_FeatureDescriptors_SkipPadding
0x18008d17f  test    rax, rax
0x18008d182  jz      short loc_18008D1CC
0x18008d184  cmp     [rax+1Dh], bl
0x18008d187  jnz     short loc_18008D193
0x18008d189  cmp     [rax+1Eh], bl
0x18008d18c  jnz     short loc_18008D193
0x18008d18e  cmp     [rax+1Ch], bl
0x18008d191  jz      short loc_18008D199
0x18008d193  lea     rcx, [rax+38h]
0x18008d197  jmp     short loc_18008D17A
0x18008d199  lea     r9, g_wil_details_featureChangeNotification
0x18008d1a0  xor     edx, edx
0x18008d1a2  lea     r8, [rsp+28h+arg_0]
0x18008d1a7  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x18008d1ae  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x18008d1b5  nop     dword ptr [rax+rax+00h]
0x18008d1ba  test    eax, eax
0x18008d1bc  jz      short loc_18008D1C7
0x18008d1be  mov     cs:g_wil_details_featureChangeNotification, rbx
0x18008d1c5  jmp     short loc_18008D1CC
0x18008d1c7  mov     ebx, 1
0x18008d1cc  call    wil_details_RegisterFeatureUsageProvider
0x18008d1d1  test    eax, eax
0x18008d1d3  jz      short loc_18008D1DE
0x18008d1d5  xor     ecx, ecx
0x18008d1d7  test    ebx, ebx
0x18008d1d9  cmovnz  eax, ecx
0x18008d1dc  jmp     short loc_18008D1E0
0x18008d1de  xor     eax, eax
0x18008d1e0  add     rsp, 20h
0x18008d1e4  pop     rbx
0x18008d1e5  retn
```
