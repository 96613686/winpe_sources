# wil_InitializeFeatureStaging

- ea: `0x18007b154`
- end: `0x18007b20b`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18007b090`

## callees

- `0x180012e5c`
- `0x18003a4ac`
- `0x18003a74c`
- `0x18007b154`
- `0x18007b214`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18007b1d2`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x18007b1d2`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18007b17c`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x18007b17c`

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
0x18007b154  push    rbx
0x18007b156  sub     rsp, 20h
0x18007b15a  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x18007b161  mov     [rsp+28h+arg_0], 0
0x18007b16a  jnz     loc_18007B202
0x18007b170  xor     ebx, ebx
0x18007b172  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x18007b17c  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x18007b183  nop     dword ptr [rax+rax+00h]
0x18007b188  mov     [rsp+28h+arg_0], rax
0x18007b18d  call    wil_details_PopulateInitialConfiguredFeatureStates
0x18007b192  call    wil_details_EvaluateFeatureDependencies
0x18007b197  lea     rcx, wil_details_featureDescriptors_a
0x18007b19e  call    wil_details_FeatureDescriptors_SkipPadding
0x18007b1a3  test    rax, rax
0x18007b1a6  jz      short loc_18007B1F0
0x18007b1a8  cmp     [rax+1Dh], bl
0x18007b1ab  jnz     short loc_18007B1B7
0x18007b1ad  cmp     [rax+1Eh], bl
0x18007b1b0  jnz     short loc_18007B1B7
0x18007b1b2  cmp     [rax+1Ch], bl
0x18007b1b5  jz      short loc_18007B1BD
0x18007b1b7  lea     rcx, [rax+38h]
0x18007b1bb  jmp     short loc_18007B19E
0x18007b1bd  lea     r9, g_wil_details_featureChangeNotification
0x18007b1c4  xor     edx, edx
0x18007b1c6  lea     r8, [rsp+28h+arg_0]
0x18007b1cb  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x18007b1d2  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x18007b1d9  nop     dword ptr [rax+rax+00h]
0x18007b1de  test    eax, eax
0x18007b1e0  jz      short loc_18007B1EB
0x18007b1e2  mov     cs:g_wil_details_featureChangeNotification, rbx
0x18007b1e9  jmp     short loc_18007B1F0
0x18007b1eb  mov     ebx, 1
0x18007b1f0  call    wil_details_RegisterFeatureUsageProvider
0x18007b1f5  test    eax, eax
0x18007b1f7  jz      short loc_18007B202
0x18007b1f9  xor     ecx, ecx
0x18007b1fb  test    ebx, ebx
0x18007b1fd  cmovnz  eax, ecx
0x18007b200  jmp     short loc_18007B204
0x18007b202  xor     eax, eax
0x18007b204  add     rsp, 20h
0x18007b208  pop     rbx
0x18007b209  retn
```
