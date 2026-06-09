# wil_InitializeFeatureStaging

- ea: `0x18008a130`
- end: `0x18008a1e7`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180089078`

## callees

- `0x18001dd20`
- `0x180051c28`
- `0x1800753e0`
- `0x18008a130`
- `0x18008a1f0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18008a1ae`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18008a1ae`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18008a158`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18008a158`

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
0x18008a130  push    rbx
0x18008a132  sub     rsp, 20h
0x18008a136  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x18008a13d  mov     [rsp+28h+arg_0], 0
0x18008a146  jnz     loc_18008A1DE
0x18008a14c  xor     ebx, ebx
0x18008a14e  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x18008a158  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x18008a15f  nop     dword ptr [rax+rax+00h]
0x18008a164  mov     [rsp+28h+arg_0], rax
0x18008a169  call    wil_details_PopulateInitialConfiguredFeatureStates
0x18008a16e  call    wil_details_EvaluateFeatureDependencies
0x18008a173  lea     rcx, wil_details_featureDescriptors_a
0x18008a17a  call    wil_details_FeatureDescriptors_SkipPadding
0x18008a17f  test    rax, rax
0x18008a182  jz      short loc_18008A1CC
0x18008a184  cmp     [rax+1Dh], bl
0x18008a187  jnz     short loc_18008A193
0x18008a189  cmp     [rax+1Eh], bl
0x18008a18c  jnz     short loc_18008A193
0x18008a18e  cmp     [rax+1Ch], bl
0x18008a191  jz      short loc_18008A199
0x18008a193  lea     rcx, [rax+38h]
0x18008a197  jmp     short loc_18008A17A
0x18008a199  lea     r9, g_wil_details_featureChangeNotification
0x18008a1a0  xor     edx, edx
0x18008a1a2  lea     r8, [rsp+28h+arg_0]
0x18008a1a7  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x18008a1ae  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x18008a1b5  nop     dword ptr [rax+rax+00h]
0x18008a1ba  test    eax, eax
0x18008a1bc  jz      short loc_18008A1C7
0x18008a1be  mov     cs:g_wil_details_featureChangeNotification, rbx
0x18008a1c5  jmp     short loc_18008A1CC
0x18008a1c7  mov     ebx, 1
0x18008a1cc  call    wil_details_RegisterFeatureUsageProvider
0x18008a1d1  test    eax, eax
0x18008a1d3  jz      short loc_18008A1DE
0x18008a1d5  xor     ecx, ecx
0x18008a1d7  test    ebx, ebx
0x18008a1d9  cmovnz  eax, ecx
0x18008a1dc  jmp     short loc_18008A1E0
0x18008a1de  xor     eax, eax
0x18008a1e0  add     rsp, 20h
0x18008a1e4  pop     rbx
0x18008a1e5  retn
```
