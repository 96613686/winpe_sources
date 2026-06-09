# wil_InitializeFeatureStaging

- ea: `0x14000d15c`
- end: `0x14000d2bd`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000d078`

## callees

- `0x14000a858`
- `0x14000d15c`
- `0x14000d2c4`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000d286`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000d286`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14000d212`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14000d212`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14000d18d`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14000d18d`

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
0x14000d15c  mov     [rsp+arg_8], rbx
0x14000d161  mov     [rsp+arg_10], rbp
0x14000d166  push    rdi
0x14000d167  sub     rsp, 40h
0x14000d16b  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000d172  mov     [rsp+48h+arg_0], 0
0x14000d17b  jnz     loc_14000D2AA
0x14000d181  xor     edi, edi
0x14000d183  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14000d18d  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14000d194  nop     dword ptr [rax+rax+00h]
0x14000d199  mov     [rsp+48h+arg_0], rax
0x14000d19e  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14000d1a3  call    wil_details_EvaluateFeatureDependencies
0x14000d1a8  lea     rbx, wil_details_featureDescriptors_a
0x14000d1af  lea     rbp, wil_details_featureDescriptors_a
0x14000d1b6  mov     rax, rbx
0x14000d1b9  cmp     rbx, rbp
0x14000d1bc  jnb     short loc_14000D230
0x14000d1be  cmp     [rax], rdi
0x14000d1c1  jnz     short loc_14000D1F6
0x14000d1c3  add     rax, 8
0x14000d1c7  cmp     rax, rbp
0x14000d1ca  jb      short loc_14000D1BE
0x14000d1cc  jmp     short loc_14000D230
0x14000d1ce  cmp     [rax+1Dh], dil
0x14000d1d2  jnz     short loc_14000D1E0
0x14000d1d4  cmp     [rax+1Eh], dil
0x14000d1d8  jnz     short loc_14000D1E0
0x14000d1da  cmp     [rax+1Ch], dil
0x14000d1de  jz      short loc_14000D1FD
0x14000d1e0  add     rax, 38h ; '8'
0x14000d1e4  jmp     short loc_14000D1EF
0x14000d1e6  cmp     [rax], rdi
0x14000d1e9  jnz     short loc_14000D1F6
0x14000d1eb  add     rax, 8
0x14000d1ef  cmp     rax, rbp
0x14000d1f2  jb      short loc_14000D1E6
0x14000d1f4  jmp     short loc_14000D230
0x14000d1f6  test    rax, rax
0x14000d1f9  jnz     short loc_14000D1CE
0x14000d1fb  jmp     short loc_14000D230
0x14000d1fd  lea     r9, g_wil_details_featureChangeNotification
0x14000d204  xor     edx, edx
0x14000d206  lea     r8, [rsp+48h+arg_0]
0x14000d20b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14000d212  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14000d219  nop     dword ptr [rax+rax+00h]
0x14000d21e  test    eax, eax
0x14000d220  jz      short loc_14000D22B
0x14000d222  mov     cs:g_wil_details_featureChangeNotification, rdi
0x14000d229  jmp     short loc_14000D230
0x14000d22b  mov     edi, 1
0x14000d230  xor     eax, eax
0x14000d232  xorps   xmm0, xmm0
0x14000d235  mov     [rsp+48h+var_18], rax
0x14000d23a  lea     rax, wil_details_RecordFeatureUsageReporting
0x14000d241  movups  [rsp+48h+var_28], xmm0
0x14000d246  mov     cs:g_wil_details_recordFeatureUsage, rax
0x14000d24d  jmp     short loc_14000D259
0x14000d24f  cmp     qword ptr [rbx], 0
0x14000d253  jnz     short loc_14000D260
0x14000d255  add     rbx, 8
0x14000d259  cmp     rbx, rbp
0x14000d25c  jb      short loc_14000D24F
0x14000d25e  xor     ebx, ebx
0x14000d260  lea     r8, g_wil_details_featureUsageProvider
0x14000d267  mov     qword ptr [rsp+48h+var_28], rbx
0x14000d26c  lea     rdx, [rsp+48h+var_28]
0x14000d271  mov     qword ptr [rsp+48h+var_28+8], rbp
0x14000d276  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x14000d27d  mov     [rsp+48h+var_18], 0
0x14000d286  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x14000d28d  nop     dword ptr [rax+rax+00h]
0x14000d292  test    eax, eax
0x14000d294  jz      short loc_14000D2AA
0x14000d296  xor     ecx, ecx
0x14000d298  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000d2a3  test    edi, edi
0x14000d2a5  cmovnz  eax, ecx
0x14000d2a8  jmp     short loc_14000D2AC
0x14000d2aa  xor     eax, eax
0x14000d2ac  mov     rbx, [rsp+48h+arg_8]
0x14000d2b1  mov     rbp, [rsp+48h+arg_10]
0x14000d2b6  add     rsp, 40h
0x14000d2ba  pop     rdi
0x14000d2bb  retn
```
