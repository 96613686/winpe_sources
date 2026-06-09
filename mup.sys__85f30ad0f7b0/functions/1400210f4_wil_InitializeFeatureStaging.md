# wil_InitializeFeatureStaging

- ea: `0x1400210f4`
- end: `0x1400211ab`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140010f18`

## callees

- `0x140003964`
- `0x140011d1c`
- `0x140011fbc`
- `0x1400210f4`
- `0x1400211b4`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140021172`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140021172`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002111c`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14002111c`

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
0x1400210f4  push    rbx
0x1400210f6  sub     rsp, 20h
0x1400210fa  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140021101  mov     [rsp+28h+arg_0], 0
0x14002110a  jnz     loc_1400211A2
0x140021110  xor     ebx, ebx
0x140021112  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14002111c  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140021123  nop     dword ptr [rax+rax+00h]
0x140021128  mov     [rsp+28h+arg_0], rax
0x14002112d  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140021132  call    wil_details_EvaluateFeatureDependencies
0x140021137  lea     rcx, wil_details_featureDescriptors_a
0x14002113e  call    wil_details_FeatureDescriptors_SkipPadding
0x140021143  test    rax, rax
0x140021146  jz      short loc_140021190
0x140021148  cmp     [rax+1Dh], bl
0x14002114b  jnz     short loc_140021157
0x14002114d  cmp     [rax+1Eh], bl
0x140021150  jnz     short loc_140021157
0x140021152  cmp     [rax+1Ch], bl
0x140021155  jz      short loc_14002115D
0x140021157  lea     rcx, [rax+38h]
0x14002115b  jmp     short loc_14002113E
0x14002115d  lea     r9, g_wil_details_featureChangeNotification
0x140021164  xor     edx, edx
0x140021166  lea     r8, [rsp+28h+arg_0]
0x14002116b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140021172  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140021179  nop     dword ptr [rax+rax+00h]
0x14002117e  test    eax, eax
0x140021180  jz      short loc_14002118B
0x140021182  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140021189  jmp     short loc_140021190
0x14002118b  mov     ebx, 1
0x140021190  call    wil_details_RegisterFeatureUsageProvider
0x140021195  test    eax, eax
0x140021197  jz      short loc_1400211A2
0x140021199  xor     ecx, ecx
0x14002119b  test    ebx, ebx
0x14002119d  cmovnz  eax, ecx
0x1400211a0  jmp     short loc_1400211A4
0x1400211a2  xor     eax, eax
0x1400211a4  add     rsp, 20h
0x1400211a8  pop     rbx
0x1400211a9  retn
```
