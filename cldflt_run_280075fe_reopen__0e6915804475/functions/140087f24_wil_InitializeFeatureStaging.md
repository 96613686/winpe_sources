# wil_InitializeFeatureStaging

- ea: `0x140087f24`
- end: `0x140087fdb`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140087490`

## callees

- `0x140009ea8`
- `0x140042cf4`
- `0x14007e198`
- `0x140087f24`
- `0x140087fe4`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140087fa2`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140087fa2`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140087f4c`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140087f4c`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // ebx
  _UNKNOWN **i; // rcx
  _BYTE *v2; // rax
  __int64 result; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( WPP_MAIN_CB.ActiveThreadCount )
    return 0;
  v0 = 0;
  WPP_MAIN_CB.ActiveThreadCount = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = &Feature_CloudFileDisguisePlaceholders__private_descriptor; ; i = (_UNKNOWN **)(v2 + 56) )
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
                           &WPP_MAIN_CB.Dpc.DeferredRoutine) )
        WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
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
0x140087f24  push    rbx
0x140087f26  sub     rsp, 20h
0x140087f2a  cmp     cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x140087f31  mov     [rsp+28h+arg_0], 0
0x140087f3a  jnz     loc_140087FD2
0x140087f40  xor     ebx, ebx
0x140087f42  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 1
0x140087f4c  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x140087f53  nop     dword ptr [rax+rax+00h]
0x140087f58  mov     [rsp+28h+arg_0], rax
0x140087f5d  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140087f62  call    wil_details_EvaluateFeatureDependencies
0x140087f67  lea     rcx, Feature_CloudFileDisguisePlaceholders__private_descriptor
0x140087f6e  call    wil_details_FeatureDescriptors_SkipPadding
0x140087f73  test    rax, rax
0x140087f76  jz      short loc_140087FC0
0x140087f78  cmp     [rax+1Dh], bl
0x140087f7b  jnz     short loc_140087F87
0x140087f7d  cmp     [rax+1Eh], bl
0x140087f80  jnz     short loc_140087F87
0x140087f82  cmp     [rax+1Ch], bl
0x140087f85  jz      short loc_140087F8D
0x140087f87  lea     rcx, [rax+38h]
0x140087f8b  jmp     short loc_140087F6E
0x140087f8d  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x140087f94  xor     edx, edx
0x140087f96  lea     r8, [rsp+28h+arg_0]
0x140087f9b  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140087fa2  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140087fa9  nop     dword ptr [rax+rax+00h]
0x140087fae  test    eax, eax
0x140087fb0  jz      short loc_140087FBB
0x140087fb2  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rbx
0x140087fb9  jmp     short loc_140087FC0
0x140087fbb  mov     ebx, 1
0x140087fc0  call    wil_details_RegisterFeatureUsageProvider
0x140087fc5  test    eax, eax
0x140087fc7  jz      short loc_140087FD2
0x140087fc9  xor     ecx, ecx
0x140087fcb  test    ebx, ebx
0x140087fcd  cmovnz  eax, ecx
0x140087fd0  jmp     short loc_140087FD4
0x140087fd2  xor     eax, eax
0x140087fd4  add     rsp, 20h
0x140087fd8  pop     rbx
0x140087fd9  retn
```
