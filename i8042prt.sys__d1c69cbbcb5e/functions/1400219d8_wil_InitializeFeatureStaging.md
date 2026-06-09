# wil_InitializeFeatureStaging

- ea: `0x1400219d8`
- end: `0x140021a91`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140021078`

## callees

- `0x14000a128`
- `0x140017c0c`
- `0x140017e5c`
- `0x1400219d8`
- `0x140021a98`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140021a58`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140021a58`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140021a00`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140021a00`

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
0x1400219d8  push    rbx
0x1400219da  sub     rsp, 20h
0x1400219de  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400219e5  mov     [rsp+28h+arg_0], 0
0x1400219ee  jnz     loc_140021A88
0x1400219f4  xor     ebx, ebx
0x1400219f6  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140021a00  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140021a07  nop     dword ptr [rax+rax+00h]
0x140021a0c  mov     [rsp+28h+arg_0], rax
0x140021a11  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140021a16  call    wil_details_EvaluateFeatureDependencies
0x140021a1b  lea     rcx, wil_details_featureDescriptors_a
0x140021a22  jmp     short loc_140021A37
0x140021a24  cmp     [rax+1Dh], bl
0x140021a27  jnz     short loc_140021A33
0x140021a29  cmp     [rax+1Eh], bl
0x140021a2c  jnz     short loc_140021A33
0x140021a2e  cmp     [rax+1Ch], bl
0x140021a31  jz      short loc_140021A43
0x140021a33  lea     rcx, [rax+38h]
0x140021a37  call    wil_details_FeatureDescriptors_SkipPadding
0x140021a3c  test    rax, rax
0x140021a3f  jnz     short loc_140021A24
0x140021a41  jmp     short loc_140021A76
0x140021a43  lea     r9, g_wil_details_featureChangeNotification
0x140021a4a  xor     edx, edx
0x140021a4c  lea     r8, [rsp+28h+arg_0]
0x140021a51  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140021a58  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140021a5f  nop     dword ptr [rax+rax+00h]
0x140021a64  test    eax, eax
0x140021a66  jz      short loc_140021A71
0x140021a68  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140021a6f  jmp     short loc_140021A76
0x140021a71  mov     ebx, 1
0x140021a76  call    wil_details_RegisterFeatureUsageProvider
0x140021a7b  test    eax, eax
0x140021a7d  jz      short loc_140021A88
0x140021a7f  xor     ecx, ecx
0x140021a81  test    ebx, ebx
0x140021a83  cmovnz  eax, ecx
0x140021a86  jmp     short loc_140021A8A
0x140021a88  xor     eax, eax
0x140021a8a  add     rsp, 20h
0x140021a8e  pop     rbx
0x140021a8f  retn
```
