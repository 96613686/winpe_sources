# wil_InitializeFeatureStaging

- ea: `0x140082078`
- end: `0x14008212f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140035cc4`

## callees

- `0x140010f04`
- `0x140036550`
- `0x14003678c`
- `0x140082078`
- `0x140082138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400820a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400820a0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400820f6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400820f6`

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
0x140082078  push    rbx
0x14008207a  sub     rsp, 20h
0x14008207e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140082085  mov     [rsp+28h+arg_0], 0
0x14008208e  jnz     loc_140082126
0x140082094  xor     ebx, ebx
0x140082096  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x1400820a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400820a7  nop     dword ptr [rax+rax+00h]
0x1400820ac  mov     [rsp+28h+arg_0], rax
0x1400820b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400820b6  call    wil_details_EvaluateFeatureDependencies
0x1400820bb  lea     rcx, wil_details_featureDescriptors_a
0x1400820c2  call    wil_details_FeatureDescriptors_SkipPadding
0x1400820c7  test    rax, rax
0x1400820ca  jz      short loc_140082114
0x1400820cc  cmp     [rax+1Dh], bl
0x1400820cf  jnz     short loc_1400820DB
0x1400820d1  cmp     [rax+1Eh], bl
0x1400820d4  jnz     short loc_1400820DB
0x1400820d6  cmp     [rax+1Ch], bl
0x1400820d9  jz      short loc_1400820E1
0x1400820db  lea     rcx, [rax+38h]
0x1400820df  jmp     short loc_1400820C2
0x1400820e1  lea     r9, g_wil_details_featureChangeNotification
0x1400820e8  xor     edx, edx
0x1400820ea  lea     r8, [rsp+28h+arg_0]
0x1400820ef  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400820f6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400820fd  nop     dword ptr [rax+rax+00h]
0x140082102  test    eax, eax
0x140082104  jz      short loc_14008210F
0x140082106  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14008210d  jmp     short loc_140082114
0x14008210f  mov     ebx, 1
0x140082114  call    wil_details_RegisterFeatureUsageProvider
0x140082119  test    eax, eax
0x14008211b  jz      short loc_140082126
0x14008211d  xor     ecx, ecx
0x14008211f  test    ebx, ebx
0x140082121  cmovnz  eax, ecx
0x140082124  jmp     short loc_140082128
0x140082126  xor     eax, eax
0x140082128  add     rsp, 20h
0x14008212c  pop     rbx
0x14008212d  retn
```
