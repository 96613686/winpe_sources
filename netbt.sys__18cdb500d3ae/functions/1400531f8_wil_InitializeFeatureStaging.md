# wil_InitializeFeatureStaging

- ea: `0x1400531f8`
- end: `0x1400532b1`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140053828`

## callees

- `0x14002d2b0`
- `0x140044d40`
- `0x140044fec`
- `0x1400531f8`
- `0x1400532b8`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140053278`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140053278`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140053220`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140053220`

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
0x1400531f8  push    rbx
0x1400531fa  sub     rsp, 20h
0x1400531fe  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140053205  mov     [rsp+28h+arg_0], 0
0x14005320e  jnz     loc_1400532A8
0x140053214  xor     ebx, ebx
0x140053216  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140053220  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140053227  nop     dword ptr [rax+rax+00h]
0x14005322c  mov     [rsp+28h+arg_0], rax
0x140053231  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140053236  call    wil_details_EvaluateFeatureDependencies
0x14005323b  lea     rcx, wil_details_featureDescriptors_a
0x140053242  jmp     short loc_140053257
0x140053244  cmp     [rax+1Dh], bl
0x140053247  jnz     short loc_140053253
0x140053249  cmp     [rax+1Eh], bl
0x14005324c  jnz     short loc_140053253
0x14005324e  cmp     [rax+1Ch], bl
0x140053251  jz      short loc_140053263
0x140053253  lea     rcx, [rax+38h]
0x140053257  call    wil_details_FeatureDescriptors_SkipPadding
0x14005325c  test    rax, rax
0x14005325f  jnz     short loc_140053244
0x140053261  jmp     short loc_140053296
0x140053263  lea     r9, g_wil_details_featureChangeNotification
0x14005326a  xor     edx, edx
0x14005326c  lea     r8, [rsp+28h+arg_0]
0x140053271  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140053278  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14005327f  nop     dword ptr [rax+rax+00h]
0x140053284  test    eax, eax
0x140053286  jz      short loc_140053291
0x140053288  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14005328f  jmp     short loc_140053296
0x140053291  mov     ebx, 1
0x140053296  call    wil_details_RegisterFeatureUsageProvider
0x14005329b  test    eax, eax
0x14005329d  jz      short loc_1400532A8
0x14005329f  xor     ecx, ecx
0x1400532a1  test    ebx, ebx
0x1400532a3  cmovnz  eax, ecx
0x1400532a6  jmp     short loc_1400532AA
0x1400532a8  xor     eax, eax
0x1400532aa  add     rsp, 20h
0x1400532ae  pop     rbx
0x1400532af  retn
```
