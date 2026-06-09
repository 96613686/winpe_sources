# wil_InitializeFeatureStaging

- ea: `0x140030078`
- end: `0x140030131`
- name: `wil_InitializeFeatureStaging`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001143c`

## callees

- `0x1400118c4`
- `0x14002f5cc`
- `0x14002f86c`
- `0x140030078`
- `0x140030138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400300a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400300a0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400300f8`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400300f8`

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
0x140030078  push    rbx
0x14003007a  sub     rsp, 20h
0x14003007e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140030085  mov     [rsp+28h+arg_0], 0
0x14003008e  jnz     loc_140030128
0x140030094  xor     ebx, ebx
0x140030096  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400300a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400300a7  nop     dword ptr [rax+rax+00h]
0x1400300ac  mov     [rsp+28h+arg_0], rax
0x1400300b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400300b6  call    wil_details_EvaluateFeatureDependencies
0x1400300bb  lea     rcx, wil_details_featureDescriptors_a
0x1400300c2  jmp     short loc_1400300D7
0x1400300c4  cmp     [rax+1Dh], bl
0x1400300c7  jnz     short loc_1400300D3
0x1400300c9  cmp     [rax+1Eh], bl
0x1400300cc  jnz     short loc_1400300D3
0x1400300ce  cmp     [rax+1Ch], bl
0x1400300d1  jz      short loc_1400300E3
0x1400300d3  lea     rcx, [rax+38h]
0x1400300d7  call    wil_details_FeatureDescriptors_SkipPadding
0x1400300dc  test    rax, rax
0x1400300df  jnz     short loc_1400300C4
0x1400300e1  jmp     short loc_140030116
0x1400300e3  lea     r9, g_wil_details_featureChangeNotification
0x1400300ea  xor     edx, edx
0x1400300ec  lea     r8, [rsp+28h+arg_0]
0x1400300f1  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400300f8  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400300ff  nop     dword ptr [rax+rax+00h]
0x140030104  test    eax, eax
0x140030106  jz      short loc_140030111
0x140030108  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14003010f  jmp     short loc_140030116
0x140030111  mov     ebx, 1
0x140030116  call    wil_details_RegisterFeatureUsageProvider
0x14003011b  test    eax, eax
0x14003011d  jz      short loc_140030128
0x14003011f  xor     ecx, ecx
0x140030121  test    ebx, ebx
0x140030123  cmovnz  eax, ecx
0x140030126  jmp     short loc_14003012A
0x140030128  xor     eax, eax
0x14003012a  add     rsp, 20h
0x14003012e  pop     rbx
0x14003012f  retn
```
