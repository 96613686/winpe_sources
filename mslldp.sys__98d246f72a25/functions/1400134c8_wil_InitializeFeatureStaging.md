# wil_InitializeFeatureStaging

- ea: `0x1400134c8`
- end: `0x140013581`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140013350`

## callees

- `0x140004c24`
- `0x14000e7a0`
- `0x14000ea4c`
- `0x1400134c8`
- `0x140013588`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140013548`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140013548`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400134f0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400134f0`

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
0x1400134c8  push    rbx
0x1400134ca  sub     rsp, 20h
0x1400134ce  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400134d5  mov     [rsp+28h+arg_0], 0
0x1400134de  jnz     loc_140013578
0x1400134e4  xor     ebx, ebx
0x1400134e6  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400134f0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400134f7  nop     dword ptr [rax+rax+00h]
0x1400134fc  mov     [rsp+28h+arg_0], rax
0x140013501  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140013506  call    wil_details_EvaluateFeatureDependencies
0x14001350b  lea     rcx, wil_details_featureDescriptors_a
0x140013512  jmp     short loc_140013527
0x140013514  cmp     [rax+1Dh], bl
0x140013517  jnz     short loc_140013523
0x140013519  cmp     [rax+1Eh], bl
0x14001351c  jnz     short loc_140013523
0x14001351e  cmp     [rax+1Ch], bl
0x140013521  jz      short loc_140013533
0x140013523  lea     rcx, [rax+38h]
0x140013527  call    wil_details_FeatureDescriptors_SkipPadding
0x14001352c  test    rax, rax
0x14001352f  jnz     short loc_140013514
0x140013531  jmp     short loc_140013566
0x140013533  lea     r9, g_wil_details_featureChangeNotification
0x14001353a  xor     edx, edx
0x14001353c  lea     r8, [rsp+28h+arg_0]
0x140013541  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140013548  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14001354f  nop     dword ptr [rax+rax+00h]
0x140013554  test    eax, eax
0x140013556  jz      short loc_140013561
0x140013558  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14001355f  jmp     short loc_140013566
0x140013561  mov     ebx, 1
0x140013566  call    wil_details_RegisterFeatureUsageProvider
0x14001356b  test    eax, eax
0x14001356d  jz      short loc_140013578
0x14001356f  xor     ecx, ecx
0x140013571  test    ebx, ebx
0x140013573  cmovnz  eax, ecx
0x140013576  jmp     short loc_14001357A
0x140013578  xor     eax, eax
0x14001357a  add     rsp, 20h
0x14001357e  pop     rbx
0x14001357f  retn
```
