# wil_InitializeFeatureStaging

- ea: `0x140055078`
- end: `0x14005512f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003108c`

## callees

- `0x14000fb30`
- `0x140033bcc`
- `0x140033e6c`
- `0x140055078`
- `0x140055138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400550a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400550a0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400550f6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400550f6`

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
0x140055078  push    rbx
0x14005507a  sub     rsp, 20h
0x14005507e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140055085  mov     [rsp+28h+arg_0], 0
0x14005508e  jnz     loc_140055126
0x140055094  xor     ebx, ebx
0x140055096  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400550a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400550a7  nop     dword ptr [rax+rax+00h]
0x1400550ac  mov     [rsp+28h+arg_0], rax
0x1400550b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400550b6  call    wil_details_EvaluateFeatureDependencies
0x1400550bb  lea     rcx, wil_details_featureDescriptors_a
0x1400550c2  call    wil_details_FeatureDescriptors_SkipPadding
0x1400550c7  test    rax, rax
0x1400550ca  jz      short loc_140055114
0x1400550cc  cmp     [rax+1Dh], bl
0x1400550cf  jnz     short loc_1400550DB
0x1400550d1  cmp     [rax+1Eh], bl
0x1400550d4  jnz     short loc_1400550DB
0x1400550d6  cmp     [rax+1Ch], bl
0x1400550d9  jz      short loc_1400550E1
0x1400550db  lea     rcx, [rax+38h]
0x1400550df  jmp     short loc_1400550C2
0x1400550e1  lea     r9, g_wil_details_featureChangeNotification
0x1400550e8  xor     edx, edx
0x1400550ea  lea     r8, [rsp+28h+arg_0]
0x1400550ef  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400550f6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400550fd  nop     dword ptr [rax+rax+00h]
0x140055102  test    eax, eax
0x140055104  jz      short loc_14005510F
0x140055106  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14005510d  jmp     short loc_140055114
0x14005510f  mov     ebx, 1
0x140055114  call    wil_details_RegisterFeatureUsageProvider
0x140055119  test    eax, eax
0x14005511b  jz      short loc_140055126
0x14005511d  xor     ecx, ecx
0x14005511f  test    ebx, ebx
0x140055121  cmovnz  eax, ecx
0x140055124  jmp     short loc_140055128
0x140055126  xor     eax, eax
0x140055128  add     rsp, 20h
0x14005512c  pop     rbx
0x14005512d  retn
```
