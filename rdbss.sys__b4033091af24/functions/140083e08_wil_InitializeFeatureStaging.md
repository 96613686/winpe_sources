# wil_InitializeFeatureStaging

- ea: `0x140083e08`
- end: `0x140083ec1`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14008321c`

## callees

- `0x14001ca94`
- `0x14004a0fc`
- `0x14004a39c`
- `0x140083e08`
- `0x140083ec8`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140083e88`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140083e88`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140083e30`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140083e30`

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
0x140083e08  push    rbx
0x140083e0a  sub     rsp, 20h
0x140083e0e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140083e15  mov     [rsp+28h+arg_0], 0
0x140083e1e  jnz     loc_140083EB8
0x140083e24  xor     ebx, ebx
0x140083e26  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140083e30  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140083e37  nop     dword ptr [rax+rax+00h]
0x140083e3c  mov     [rsp+28h+arg_0], rax
0x140083e41  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140083e46  call    wil_details_EvaluateFeatureDependencies
0x140083e4b  lea     rcx, wil_details_featureDescriptors_a
0x140083e52  jmp     short loc_140083E67
0x140083e54  cmp     [rax+1Dh], bl
0x140083e57  jnz     short loc_140083E63
0x140083e59  cmp     [rax+1Eh], bl
0x140083e5c  jnz     short loc_140083E63
0x140083e5e  cmp     [rax+1Ch], bl
0x140083e61  jz      short loc_140083E73
0x140083e63  lea     rcx, [rax+38h]
0x140083e67  call    wil_details_FeatureDescriptors_SkipPadding
0x140083e6c  test    rax, rax
0x140083e6f  jnz     short loc_140083E54
0x140083e71  jmp     short loc_140083EA6
0x140083e73  lea     r9, g_wil_details_featureChangeNotification
0x140083e7a  xor     edx, edx
0x140083e7c  lea     r8, [rsp+28h+arg_0]
0x140083e81  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140083e88  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140083e8f  nop     dword ptr [rax+rax+00h]
0x140083e94  test    eax, eax
0x140083e96  jz      short loc_140083EA1
0x140083e98  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140083e9f  jmp     short loc_140083EA6
0x140083ea1  mov     ebx, 1
0x140083ea6  call    wil_details_RegisterFeatureUsageProvider
0x140083eab  test    eax, eax
0x140083ead  jz      short loc_140083EB8
0x140083eaf  xor     ecx, ecx
0x140083eb1  test    ebx, ebx
0x140083eb3  cmovnz  eax, ecx
0x140083eb6  jmp     short loc_140083EBA
0x140083eb8  xor     eax, eax
0x140083eba  add     rsp, 20h
0x140083ebe  pop     rbx
0x140083ebf  retn
```
