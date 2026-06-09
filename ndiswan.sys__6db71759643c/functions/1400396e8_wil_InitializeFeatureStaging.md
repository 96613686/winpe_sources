# wil_InitializeFeatureStaging

- ea: `0x1400396e8`
- end: `0x14003979f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140039008`

## callees

- `0x14000b5a4`
- `0x14003758c`
- `0x14003782c`
- `0x1400396e8`
- `0x140039a50`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140039766`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140039766`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140039710`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140039710`

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
0x1400396e8  push    rbx
0x1400396ea  sub     rsp, 20h
0x1400396ee  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400396f5  mov     [rsp+28h+arg_0], 0
0x1400396fe  jnz     loc_140039796
0x140039704  xor     ebx, ebx
0x140039706  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140039710  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140039717  nop     dword ptr [rax+rax+00h]
0x14003971c  mov     [rsp+28h+arg_0], rax
0x140039721  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140039726  call    wil_details_EvaluateFeatureDependencies
0x14003972b  lea     rcx, wil_details_featureDescriptors_a
0x140039732  call    wil_details_FeatureDescriptors_SkipPadding
0x140039737  test    rax, rax
0x14003973a  jz      short loc_140039784
0x14003973c  cmp     [rax+1Dh], bl
0x14003973f  jnz     short loc_14003974B
0x140039741  cmp     [rax+1Eh], bl
0x140039744  jnz     short loc_14003974B
0x140039746  cmp     [rax+1Ch], bl
0x140039749  jz      short loc_140039751
0x14003974b  lea     rcx, [rax+38h]
0x14003974f  jmp     short loc_140039732
0x140039751  lea     r9, g_wil_details_featureChangeNotification
0x140039758  xor     edx, edx
0x14003975a  lea     r8, [rsp+28h+arg_0]
0x14003975f  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140039766  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14003976d  nop     dword ptr [rax+rax+00h]
0x140039772  test    eax, eax
0x140039774  jz      short loc_14003977F
0x140039776  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14003977d  jmp     short loc_140039784
0x14003977f  mov     ebx, 1
0x140039784  call    wil_details_RegisterFeatureUsageProvider
0x140039789  test    eax, eax
0x14003978b  jz      short loc_140039796
0x14003978d  xor     ecx, ecx
0x14003978f  test    ebx, ebx
0x140039791  cmovnz  eax, ecx
0x140039794  jmp     short loc_140039798
0x140039796  xor     eax, eax
0x140039798  add     rsp, 20h
0x14003979c  pop     rbx
0x14003979d  retn
```
