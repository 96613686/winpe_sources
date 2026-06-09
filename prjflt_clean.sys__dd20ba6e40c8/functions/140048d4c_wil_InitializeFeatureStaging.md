# wil_InitializeFeatureStaging

- ea: `0x140048d4c`
- end: `0x140048ead`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400484e0`

## callees

- `0x140041628`
- `0x140048d4c`
- `0x140048eb4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140048d7d`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140048d7d`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140048e02`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140048e02`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140048e76`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140048e76`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  _QWORD *v0; // rbx
  __int64 result; // rax
  __int128 v2; // [rsp+20h] [rbp-28h] BYREF
  __int64 v3; // [rsp+30h] [rbp-18h]

  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v0 = wil_details_featureDescriptors_a;
  v3 = 0;
  v2 = 0;
  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  while ( v0 < wil_details_featureDescriptors_a )
  {
    if ( *v0 )
      goto LABEL_7;
    ++v0;
  }
  v0 = 0;
LABEL_7:
  *(_QWORD *)&v2 = v0;
  *((_QWORD *)&v2 + 1) = wil_details_featureDescriptors_a;
  v3 = 0;
  result = RtlRegisterFeatureUsageProvider(
             wil_details_OnFeatureUsageProviderFlushNotification,
             &v2,
             &g_wil_details_featureUsageProvider);
  if ( !(_DWORD)result )
    return 0;
  g_wil_details_featureUsageProvider = 0;
  return result;
}

```

## disassembly

```asm
0x140048d4c  mov     [rsp+arg_8], rbx
0x140048d51  mov     [rsp+arg_10], rbp
0x140048d56  push    rdi
0x140048d57  sub     rsp, 40h
0x140048d5b  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140048d62  mov     [rsp+48h+arg_0], 0
0x140048d6b  jnz     loc_140048E9A
0x140048d71  xor     edi, edi
0x140048d73  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140048d7d  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140048d84  nop     dword ptr [rax+rax+00h]
0x140048d89  mov     [rsp+48h+arg_0], rax
0x140048d8e  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140048d93  call    wil_details_EvaluateFeatureDependencies
0x140048d98  lea     rbx, wil_details_featureDescriptors_a
0x140048d9f  lea     rbp, wil_details_featureDescriptors_a
0x140048da6  mov     rax, rbx
0x140048da9  cmp     rbx, rbp
0x140048dac  jnb     short loc_140048E20
0x140048dae  cmp     [rax], rdi
0x140048db1  jnz     short loc_140048DE6
0x140048db3  add     rax, 8
0x140048db7  cmp     rax, rbp
0x140048dba  jb      short loc_140048DAE
0x140048dbc  jmp     short loc_140048E20
0x140048dbe  cmp     [rax+1Dh], dil
0x140048dc2  jnz     short loc_140048DD0
0x140048dc4  cmp     [rax+1Eh], dil
0x140048dc8  jnz     short loc_140048DD0
0x140048dca  cmp     [rax+1Ch], dil
0x140048dce  jz      short loc_140048DED
0x140048dd0  add     rax, 38h ; '8'
0x140048dd4  jmp     short loc_140048DDF
0x140048dd6  cmp     [rax], rdi
0x140048dd9  jnz     short loc_140048DE6
0x140048ddb  add     rax, 8
0x140048ddf  cmp     rax, rbp
0x140048de2  jb      short loc_140048DD6
0x140048de4  jmp     short loc_140048E20
0x140048de6  test    rax, rax
0x140048de9  jnz     short loc_140048DBE
0x140048deb  jmp     short loc_140048E20
0x140048ded  lea     r9, g_wil_details_featureChangeNotification
0x140048df4  xor     edx, edx
0x140048df6  lea     r8, [rsp+48h+arg_0]
0x140048dfb  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140048e02  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140048e09  nop     dword ptr [rax+rax+00h]
0x140048e0e  test    eax, eax
0x140048e10  jz      short loc_140048E1B
0x140048e12  mov     cs:g_wil_details_featureChangeNotification, rdi
0x140048e19  jmp     short loc_140048E20
0x140048e1b  mov     edi, 1
0x140048e20  xor     eax, eax
0x140048e22  xorps   xmm0, xmm0
0x140048e25  mov     [rsp+48h+var_18], rax
0x140048e2a  lea     rax, wil_details_RecordFeatureUsageReporting
0x140048e31  movups  [rsp+48h+var_28], xmm0
0x140048e36  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140048e3d  jmp     short loc_140048E49
0x140048e3f  cmp     qword ptr [rbx], 0
0x140048e43  jnz     short loc_140048E50
0x140048e45  add     rbx, 8
0x140048e49  cmp     rbx, rbp
0x140048e4c  jb      short loc_140048E3F
0x140048e4e  xor     ebx, ebx
0x140048e50  lea     r8, g_wil_details_featureUsageProvider
0x140048e57  mov     qword ptr [rsp+48h+var_28], rbx
0x140048e5c  lea     rdx, [rsp+48h+var_28]
0x140048e61  mov     qword ptr [rsp+48h+var_28+8], rbp
0x140048e66  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140048e6d  mov     [rsp+48h+var_18], 0
0x140048e76  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140048e7d  nop     dword ptr [rax+rax+00h]
0x140048e82  test    eax, eax
0x140048e84  jz      short loc_140048E9A
0x140048e86  xor     ecx, ecx
0x140048e88  mov     cs:g_wil_details_featureUsageProvider, 0
0x140048e93  test    edi, edi
0x140048e95  cmovnz  eax, ecx
0x140048e98  jmp     short loc_140048E9C
0x140048e9a  xor     eax, eax
0x140048e9c  mov     rbx, [rsp+48h+arg_8]
0x140048ea1  mov     rbp, [rsp+48h+arg_10]
0x140048ea6  add     rsp, 40h
0x140048eaa  pop     rdi
0x140048eab  retn
```
