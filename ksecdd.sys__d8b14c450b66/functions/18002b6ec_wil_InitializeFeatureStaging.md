# wil_InitializeFeatureStaging

- ea: `0x18002b6ec`
- end: `0x18002b7a3`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b078`

## callees

- `0x18000b834`
- `0x180021424`
- `0x18002166c`
- `0x18002b6ec`
- `0x18002b7ac`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18002b714`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18002b714`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18002b76a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18002b76a`

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
  for ( i = Feature_Schannel_SslCopyTlsExtensions__private_descriptor; ; i = (int **)(v2 + 56) )
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
0x18002b6ec  push    rbx
0x18002b6ee  sub     rsp, 20h
0x18002b6f2  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x18002b6f9  mov     [rsp+28h+arg_0], 0
0x18002b702  jnz     loc_18002B79A
0x18002b708  xor     ebx, ebx
0x18002b70a  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x18002b714  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x18002b71b  nop     dword ptr [rax+rax+00h]
0x18002b720  mov     [rsp+28h+arg_0], rax
0x18002b725  call    wil_details_PopulateInitialConfiguredFeatureStates
0x18002b72a  call    wil_details_EvaluateFeatureDependencies
0x18002b72f  lea     rcx, Feature_Schannel_SslCopyTlsExtensions__private_descriptor
0x18002b736  call    wil_details_FeatureDescriptors_SkipPadding
0x18002b73b  test    rax, rax
0x18002b73e  jz      short loc_18002B788
0x18002b740  cmp     [rax+1Dh], bl
0x18002b743  jnz     short loc_18002B74F
0x18002b745  cmp     [rax+1Eh], bl
0x18002b748  jnz     short loc_18002B74F
0x18002b74a  cmp     [rax+1Ch], bl
0x18002b74d  jz      short loc_18002B755
0x18002b74f  lea     rcx, [rax+38h]
0x18002b753  jmp     short loc_18002B736
0x18002b755  lea     r9, g_wil_details_featureChangeNotification
0x18002b75c  xor     edx, edx
0x18002b75e  lea     r8, [rsp+28h+arg_0]
0x18002b763  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x18002b76a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x18002b771  nop     dword ptr [rax+rax+00h]
0x18002b776  test    eax, eax
0x18002b778  jz      short loc_18002B783
0x18002b77a  mov     cs:g_wil_details_featureChangeNotification, rbx
0x18002b781  jmp     short loc_18002B788
0x18002b783  mov     ebx, 1
0x18002b788  call    wil_details_RegisterFeatureUsageProvider
0x18002b78d  test    eax, eax
0x18002b78f  jz      short loc_18002B79A
0x18002b791  xor     ecx, ecx
0x18002b793  test    ebx, ebx
0x18002b795  cmovnz  eax, ecx
0x18002b798  jmp     short loc_18002B79C
0x18002b79a  xor     eax, eax
0x18002b79c  add     rsp, 20h
0x18002b7a0  pop     rbx
0x18002b7a1  retn
```
