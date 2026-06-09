# wil_InitializeFeatureStaging

- ea: `0x180045078`
- end: `0x18004512f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800385f0`

## callees

- `0x18001da84`
- `0x18003923c`
- `0x18003948c`
- `0x180045078`
- `0x180045138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1800450a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1800450a0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1800450f6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1800450f6`

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
                           &WPP_MAIN_CB.DeviceObjectExtension) )
        WPP_MAIN_CB.DeviceObjectExtension = 0;
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
0x180045078  push    rbx
0x18004507a  sub     rsp, 20h
0x18004507e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x180045085  mov     [rsp+28h+arg_0], 0
0x18004508e  jnz     loc_180045126
0x180045094  xor     ebx, ebx
0x180045096  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1800450a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1800450a7  nop     dword ptr [rax+rax+00h]
0x1800450ac  mov     [rsp+28h+arg_0], rax
0x1800450b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1800450b6  call    wil_details_EvaluateFeatureDependencies
0x1800450bb  lea     rcx, wil_details_featureDescriptors_a
0x1800450c2  call    wil_details_FeatureDescriptors_SkipPadding
0x1800450c7  test    rax, rax
0x1800450ca  jz      short loc_180045114
0x1800450cc  cmp     [rax+1Dh], bl
0x1800450cf  jnz     short loc_1800450DB
0x1800450d1  cmp     [rax+1Eh], bl
0x1800450d4  jnz     short loc_1800450DB
0x1800450d6  cmp     [rax+1Ch], bl
0x1800450d9  jz      short loc_1800450E1
0x1800450db  lea     rcx, [rax+38h]
0x1800450df  jmp     short loc_1800450C2
0x1800450e1  lea     r9, WPP_MAIN_CB.DeviceObjectExtension
0x1800450e8  xor     edx, edx
0x1800450ea  lea     r8, [rsp+28h+arg_0]
0x1800450ef  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1800450f6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1800450fd  nop     dword ptr [rax+rax+00h]
0x180045102  test    eax, eax
0x180045104  jz      short loc_18004510F
0x180045106  mov     cs:WPP_MAIN_CB.DeviceObjectExtension, rbx
0x18004510d  jmp     short loc_180045114
0x18004510f  mov     ebx, 1
0x180045114  call    wil_details_RegisterFeatureUsageProvider
0x180045119  test    eax, eax
0x18004511b  jz      short loc_180045126
0x18004511d  xor     ecx, ecx
0x18004511f  test    ebx, ebx
0x180045121  cmovnz  eax, ecx
0x180045124  jmp     short loc_180045128
0x180045126  xor     eax, eax
0x180045128  add     rsp, 20h
0x18004512c  pop     rbx
0x18004512d  retn
```
