# wil_InitializeFeatureStaging

- ea: `0x14000e15c`
- end: `0x14000e2bd`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000e078`

## callees

- `0x14000b858`
- `0x14000e15c`
- `0x14000e2c4`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000e286`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x14000e286`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14000e212`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14000e212`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14000e18d`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14000e18d`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // edi
  __int64 **v1; // rbx
  __int64 **v2; // rax
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = 0;
  if ( g_wil_details_isFeatureStagingInitialized )
    return 0;
  v0 = 0;
  g_wil_details_isFeatureStagingInitialized = 1;
  v6 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v1 = wil_details_featureDescriptors_a;
  v2 = wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (__int64 **)wil_details_featureDescriptors_z )
  {
    while ( !*v2 )
    {
      if ( ++v2 >= (__int64 **)wil_details_featureDescriptors_z )
        goto LABEL_19;
    }
LABEL_14:
    if ( v2 )
    {
      if ( *((_BYTE *)v2 + 29) || *((_BYTE *)v2 + 30) || *((_BYTE *)v2 + 28) )
      {
        for ( v2 += 7; v2 < (__int64 **)wil_details_featureDescriptors_z; ++v2 )
        {
          if ( *v2 )
            goto LABEL_14;
        }
      }
      else if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                                wil_details_ReevaluateOnFeatureConfigurationChange,
                                0,
                                &v6,
                                &g_wil_details_featureChangeNotification) )
      {
        g_wil_details_featureChangeNotification = 0;
      }
      else
      {
        v0 = 1;
      }
    }
  }
LABEL_19:
  v5 = 0;
  v4 = 0;
  g_wil_details_recordFeatureUsage = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))wil_details_RecordFeatureUsageReporting;
  while ( v1 < (__int64 **)wil_details_featureDescriptors_z )
  {
    if ( *v1 )
      goto LABEL_24;
    ++v1;
  }
  v1 = 0;
LABEL_24:
  *(_QWORD *)&v4 = v1;
  *((_QWORD *)&v4 + 1) = wil_details_featureDescriptors_z;
  v5 = 0;
  result = RtlRegisterFeatureUsageProvider(
             wil_details_OnFeatureUsageProviderFlushNotification,
             &v4,
             &g_wil_details_featureUsageProvider);
  if ( !(_DWORD)result )
    return 0;
  g_wil_details_featureUsageProvider = 0;
  if ( v0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14000e15c  mov     [rsp+arg_8], rbx
0x14000e161  mov     [rsp+arg_10], rbp
0x14000e166  push    rdi
0x14000e167  sub     rsp, 40h
0x14000e16b  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000e172  mov     [rsp+48h+arg_0], 0
0x14000e17b  jnz     loc_14000E2AA
0x14000e181  xor     edi, edi
0x14000e183  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14000e18d  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14000e194  nop     dword ptr [rax+rax+00h]
0x14000e199  mov     [rsp+48h+arg_0], rax
0x14000e19e  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14000e1a3  call    wil_details_EvaluateFeatureDependencies
0x14000e1a8  lea     rbx, wil_details_featureDescriptors_a
0x14000e1af  lea     rbp, wil_details_featureDescriptors_z
0x14000e1b6  mov     rax, rbx
0x14000e1b9  cmp     rbx, rbp
0x14000e1bc  jnb     short loc_14000E230
0x14000e1be  cmp     [rax], rdi
0x14000e1c1  jnz     short loc_14000E1F6
0x14000e1c3  add     rax, 8
0x14000e1c7  cmp     rax, rbp
0x14000e1ca  jb      short loc_14000E1BE
0x14000e1cc  jmp     short loc_14000E230
0x14000e1ce  cmp     [rax+1Dh], dil
0x14000e1d2  jnz     short loc_14000E1E0
0x14000e1d4  cmp     [rax+1Eh], dil
0x14000e1d8  jnz     short loc_14000E1E0
0x14000e1da  cmp     [rax+1Ch], dil
0x14000e1de  jz      short loc_14000E1FD
0x14000e1e0  add     rax, 38h ; '8'
0x14000e1e4  jmp     short loc_14000E1EF
0x14000e1e6  cmp     [rax], rdi
0x14000e1e9  jnz     short loc_14000E1F6
0x14000e1eb  add     rax, 8
0x14000e1ef  cmp     rax, rbp
0x14000e1f2  jb      short loc_14000E1E6
0x14000e1f4  jmp     short loc_14000E230
0x14000e1f6  test    rax, rax
0x14000e1f9  jnz     short loc_14000E1CE
0x14000e1fb  jmp     short loc_14000E230
0x14000e1fd  lea     r9, g_wil_details_featureChangeNotification
0x14000e204  xor     edx, edx
0x14000e206  lea     r8, [rsp+48h+arg_0]
0x14000e20b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14000e212  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14000e219  nop     dword ptr [rax+rax+00h]
0x14000e21e  test    eax, eax
0x14000e220  jz      short loc_14000E22B
0x14000e222  mov     cs:g_wil_details_featureChangeNotification, rdi
0x14000e229  jmp     short loc_14000E230
0x14000e22b  mov     edi, 1
0x14000e230  xor     eax, eax
0x14000e232  xorps   xmm0, xmm0
0x14000e235  mov     [rsp+48h+var_18], rax
0x14000e23a  lea     rax, wil_details_RecordFeatureUsageReporting
0x14000e241  movups  [rsp+48h+var_28], xmm0
0x14000e246  mov     cs:g_wil_details_recordFeatureUsage, rax
0x14000e24d  jmp     short loc_14000E259
0x14000e24f  cmp     qword ptr [rbx], 0
0x14000e253  jnz     short loc_14000E260
0x14000e255  add     rbx, 8
0x14000e259  cmp     rbx, rbp
0x14000e25c  jb      short loc_14000E24F
0x14000e25e  xor     ebx, ebx
0x14000e260  lea     r8, g_wil_details_featureUsageProvider
0x14000e267  mov     qword ptr [rsp+48h+var_28], rbx
0x14000e26c  lea     rdx, [rsp+48h+var_28]
0x14000e271  mov     qword ptr [rsp+48h+var_28+8], rbp
0x14000e276  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x14000e27d  mov     [rsp+48h+var_18], 0
0x14000e286  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x14000e28d  nop     dword ptr [rax+rax+00h]
0x14000e292  test    eax, eax
0x14000e294  jz      short loc_14000E2AA
0x14000e296  xor     ecx, ecx
0x14000e298  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000e2a3  test    edi, edi
0x14000e2a5  cmovnz  eax, ecx
0x14000e2a8  jmp     short loc_14000E2AC
0x14000e2aa  xor     eax, eax
0x14000e2ac  mov     rbx, [rsp+48h+arg_8]
0x14000e2b1  mov     rbp, [rsp+48h+arg_10]
0x14000e2b6  add     rsp, 40h
0x14000e2ba  pop     rdi
0x14000e2bb  retn
```
