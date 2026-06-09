# wil_InitializeFeatureStaging

- ea: `0x140012354`
- end: `0x1400124b5`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012200`

## callees

- `0x14000ad9c`
- `0x140012354`
- `0x1400124bc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140012385`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140012385`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001240a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14001240a`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14001247e`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14001247e`

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
0x140012354  mov     [rsp+arg_8], rbx
0x140012359  mov     [rsp+arg_10], rbp
0x14001235e  push    rdi
0x14001235f  sub     rsp, 40h
0x140012363  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14001236a  mov     [rsp+48h+arg_0], 0
0x140012373  jnz     loc_1400124A2
0x140012379  xor     edi, edi
0x14001237b  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x140012385  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14001238c  nop     dword ptr [rax+rax+00h]
0x140012391  mov     [rsp+48h+arg_0], rax
0x140012396  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14001239b  call    wil_details_EvaluateFeatureDependencies
0x1400123a0  lea     rbx, wil_details_featureDescriptors_a
0x1400123a7  lea     rbp, wil_details_featureDescriptors_a
0x1400123ae  mov     rax, rbx
0x1400123b1  cmp     rbx, rbp
0x1400123b4  jnb     short loc_140012428
0x1400123b6  cmp     [rax], rdi
0x1400123b9  jnz     short loc_1400123EE
0x1400123bb  add     rax, 8
0x1400123bf  cmp     rax, rbp
0x1400123c2  jb      short loc_1400123B6
0x1400123c4  jmp     short loc_140012428
0x1400123c6  cmp     [rax+1Dh], dil
0x1400123ca  jnz     short loc_1400123D8
0x1400123cc  cmp     [rax+1Eh], dil
0x1400123d0  jnz     short loc_1400123D8
0x1400123d2  cmp     [rax+1Ch], dil
0x1400123d6  jz      short loc_1400123F5
0x1400123d8  add     rax, 38h ; '8'
0x1400123dc  jmp     short loc_1400123E7
0x1400123de  cmp     [rax], rdi
0x1400123e1  jnz     short loc_1400123EE
0x1400123e3  add     rax, 8
0x1400123e7  cmp     rax, rbp
0x1400123ea  jb      short loc_1400123DE
0x1400123ec  jmp     short loc_140012428
0x1400123ee  test    rax, rax
0x1400123f1  jnz     short loc_1400123C6
0x1400123f3  jmp     short loc_140012428
0x1400123f5  lea     r9, g_wil_details_featureChangeNotification
0x1400123fc  xor     edx, edx
0x1400123fe  lea     r8, [rsp+48h+arg_0]
0x140012403  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14001240a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140012411  nop     dword ptr [rax+rax+00h]
0x140012416  test    eax, eax
0x140012418  jz      short loc_140012423
0x14001241a  mov     cs:g_wil_details_featureChangeNotification, rdi
0x140012421  jmp     short loc_140012428
0x140012423  mov     edi, 1
0x140012428  xor     eax, eax
0x14001242a  xorps   xmm0, xmm0
0x14001242d  mov     [rsp+48h+var_18], rax
0x140012432  lea     rax, wil_details_RecordFeatureUsageReporting
0x140012439  movups  [rsp+48h+var_28], xmm0
0x14001243e  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140012445  jmp     short loc_140012451
0x140012447  cmp     qword ptr [rbx], 0
0x14001244b  jnz     short loc_140012458
0x14001244d  add     rbx, 8
0x140012451  cmp     rbx, rbp
0x140012454  jb      short loc_140012447
0x140012456  xor     ebx, ebx
0x140012458  lea     r8, g_wil_details_featureUsageProvider
0x14001245f  mov     qword ptr [rsp+48h+var_28], rbx
0x140012464  lea     rdx, [rsp+48h+var_28]
0x140012469  mov     qword ptr [rsp+48h+var_28+8], rbp
0x14001246e  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140012475  mov     [rsp+48h+var_18], 0
0x14001247e  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140012485  nop     dword ptr [rax+rax+00h]
0x14001248a  test    eax, eax
0x14001248c  jz      short loc_1400124A2
0x14001248e  xor     ecx, ecx
0x140012490  mov     cs:g_wil_details_featureUsageProvider, 0
0x14001249b  test    edi, edi
0x14001249d  cmovnz  eax, ecx
0x1400124a0  jmp     short loc_1400124A4
0x1400124a2  xor     eax, eax
0x1400124a4  mov     rbx, [rsp+48h+arg_8]
0x1400124a9  mov     rbp, [rsp+48h+arg_10]
0x1400124ae  add     rsp, 40h
0x1400124b2  pop     rdi
0x1400124b3  retn
```
