# wil_InitializeFeatureStaging

- ea: `0x14009a078`
- end: `0x14009a12f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14007fd3c`

## callees

- `0x14003c8c0`
- `0x14008179c`
- `0x140081a3c`
- `0x14009a078`
- `0x14009a138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14009a0a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x14009a0a0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14009a0f6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14009a0f6`

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
  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v2 + 56) )
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
0x14009a078  push    rbx
0x14009a07a  sub     rsp, 20h
0x14009a07e  cmp     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14009a085  mov     [rsp+28h+arg_0], 0
0x14009a08e  jnz     loc_14009A126
0x14009a094  xor     ebx, ebx
0x14009a096  mov     cs:g_wil_details_isFeatureStagingInitialized, 1
0x14009a0a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14009a0a7  nop     dword ptr [rax+rax+00h]
0x14009a0ac  mov     [rsp+28h+arg_0], rax
0x14009a0b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x14009a0b6  call    wil_details_EvaluateFeatureDependencies
0x14009a0bb  lea     rcx, wil_details_featureDescriptors_a
0x14009a0c2  call    wil_details_FeatureDescriptors_SkipPadding
0x14009a0c7  test    rax, rax
0x14009a0ca  jz      short loc_14009A114
0x14009a0cc  cmp     [rax+1Dh], bl
0x14009a0cf  jnz     short loc_14009A0DB
0x14009a0d1  cmp     [rax+1Eh], bl
0x14009a0d4  jnz     short loc_14009A0DB
0x14009a0d6  cmp     [rax+1Ch], bl
0x14009a0d9  jz      short loc_14009A0E1
0x14009a0db  lea     rcx, [rax+38h]
0x14009a0df  jmp     short loc_14009A0C2
0x14009a0e1  lea     r9, g_wil_details_featureChangeNotification
0x14009a0e8  xor     edx, edx
0x14009a0ea  lea     r8, [rsp+28h+arg_0]
0x14009a0ef  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14009a0f6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x14009a0fd  nop     dword ptr [rax+rax+00h]
0x14009a102  test    eax, eax
0x14009a104  jz      short loc_14009A10F
0x14009a106  mov     cs:g_wil_details_featureChangeNotification, rbx
0x14009a10d  jmp     short loc_14009A114
0x14009a10f  mov     ebx, 1
0x14009a114  call    wil_details_RegisterFeatureUsageProvider
0x14009a119  test    eax, eax
0x14009a11b  jz      short loc_14009A126
0x14009a11d  xor     ecx, ecx
0x14009a11f  test    ebx, ebx
0x14009a121  cmovnz  eax, ecx
0x14009a124  jmp     short loc_14009A128
0x14009a126  xor     eax, eax
0x14009a128  add     rsp, 20h
0x14009a12c  pop     rbx
0x14009a12d  retn
```
