# wil_InitializeFeatureStaging

- ea: `0x140028088`
- end: `0x1400281e9`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140024470`

## callees

- `0x140024770`
- `0x140028088`
- `0x1400281f0`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400281b2`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400281b2`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002813e`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14002813e`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400280b9`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400280b9`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  __int64 *v0; // rbx
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
0x140028088  mov     [rsp+arg_8], rbx
0x14002808d  mov     [rsp+arg_10], rbp
0x140028092  push    rdi
0x140028093  sub     rsp, 40h
0x140028097  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002809e  mov     [rsp+48h+arg_0], 0
0x1400280a7  jnz     loc_1400281D6
0x1400280ad  xor     edi, edi
0x1400280af  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400280b9  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400280c0  nop     dword ptr [rax+rax+00h]
0x1400280c5  mov     [rsp+48h+arg_0], rax
0x1400280ca  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400280cf  call    wil_details_EvaluateFeatureDependencies
0x1400280d4  lea     rbx, wil_details_featureDescriptors_a
0x1400280db  lea     rbp, wil_details_featureDescriptors_a
0x1400280e2  mov     rax, rbx
0x1400280e5  cmp     rbx, rbp
0x1400280e8  jnb     short loc_14002815C
0x1400280ea  cmp     [rax], rdi
0x1400280ed  jnz     short loc_140028122
0x1400280ef  add     rax, 8
0x1400280f3  cmp     rax, rbp
0x1400280f6  jb      short loc_1400280EA
0x1400280f8  jmp     short loc_14002815C
0x1400280fa  cmp     [rax+1Dh], dil
0x1400280fe  jnz     short loc_14002810C
0x140028100  cmp     [rax+1Eh], dil
0x140028104  jnz     short loc_14002810C
0x140028106  cmp     [rax+1Ch], dil
0x14002810a  jz      short loc_140028129
0x14002810c  add     rax, 38h ; '8'
0x140028110  jmp     short loc_14002811B
0x140028112  cmp     [rax], rdi
0x140028115  jnz     short loc_140028122
0x140028117  add     rax, 8
0x14002811b  cmp     rax, rbp
0x14002811e  jb      short loc_140028112
0x140028120  jmp     short loc_14002815C
0x140028122  test    rax, rax
0x140028125  jnz     short loc_1400280FA
0x140028127  jmp     short loc_14002815C
0x140028129  lea     r9, g_wil_details_featureChangeNotification
0x140028130  xor     edx, edx
0x140028132  lea     r8, [rsp+48h+arg_0]
0x140028137  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14002813e  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140028145  nop     dword ptr [rax+rax+00h]
0x14002814a  test    eax, eax
0x14002814c  jz      short loc_140028157
0x14002814e  mov     cs:g_wil_details_featureChangeNotification, rdi
0x140028155  jmp     short loc_14002815C
0x140028157  mov     edi, 1
0x14002815c  xor     eax, eax
0x14002815e  xorps   xmm0, xmm0
0x140028161  mov     [rsp+48h+var_18], rax
0x140028166  lea     rax, wil_details_RecordFeatureUsageReporting
0x14002816d  movups  [rsp+48h+var_28], xmm0
0x140028172  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140028179  jmp     short loc_140028185
0x14002817b  cmp     qword ptr [rbx], 0
0x14002817f  jnz     short loc_14002818C
0x140028181  add     rbx, 8
0x140028185  cmp     rbx, rbp
0x140028188  jb      short loc_14002817B
0x14002818a  xor     ebx, ebx
0x14002818c  lea     r8, g_wil_details_featureUsageProvider
0x140028193  mov     qword ptr [rsp+48h+var_28], rbx
0x140028198  lea     rdx, [rsp+48h+var_28]
0x14002819d  mov     qword ptr [rsp+48h+var_28+8], rbp
0x1400281a2  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x1400281a9  mov     [rsp+48h+var_18], 0
0x1400281b2  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x1400281b9  nop     dword ptr [rax+rax+00h]
0x1400281be  test    eax, eax
0x1400281c0  jz      short loc_1400281D6
0x1400281c2  xor     ecx, ecx
0x1400281c4  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400281cf  test    edi, edi
0x1400281d1  cmovnz  eax, ecx
0x1400281d4  jmp     short loc_1400281D8
0x1400281d6  xor     eax, eax
0x1400281d8  mov     rbx, [rsp+48h+arg_8]
0x1400281dd  mov     rbp, [rsp+48h+arg_10]
0x1400281e2  add     rsp, 40h
0x1400281e6  pop     rdi
0x1400281e7  retn
```
