# wil_InitializeFeatureStaging

- ea: `0x14006509c`
- end: `0x140065153`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140056a40`

## callees

- `0x1400280e4`
- `0x14005adc0`
- `0x14005b06c`
- `0x14006509c`
- `0x14006515c`

## import_xrefs

- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14006511a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14006511a`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400650c4`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400650c4`

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
  if ( *(_DWORD *)&WPP_MAIN_CB.SectorSize )
    return 0;
  v0 = 0;
  *(_DWORD *)&WPP_MAIN_CB.SectorSize = 1;
  v4 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 56) )
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
                           &WPP_MAIN_CB.DeviceLock.Header.WaitListHead) )
        WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = 0;
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
0x14006509c  push    rbx
0x14006509e  sub     rsp, 20h
0x1400650a2  cmp     dword ptr cs:WPP_MAIN_CB.SectorSize, 0
0x1400650a9  mov     [rsp+28h+arg_0], 0
0x1400650b2  jnz     loc_14006514A
0x1400650b8  xor     ebx, ebx
0x1400650ba  mov     dword ptr cs:WPP_MAIN_CB.SectorSize, 1
0x1400650c4  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400650cb  nop     dword ptr [rax+rax+00h]
0x1400650d0  mov     [rsp+28h+arg_0], rax
0x1400650d5  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400650da  call    wil_details_EvaluateFeatureDependencies
0x1400650df  lea     rcx, wil_details_featureDescriptors_a
0x1400650e6  call    wil_details_FeatureDescriptors_SkipPadding
0x1400650eb  test    rax, rax
0x1400650ee  jz      short loc_140065138
0x1400650f0  cmp     [rax+1Dh], bl
0x1400650f3  jnz     short loc_1400650FF
0x1400650f5  cmp     [rax+1Eh], bl
0x1400650f8  jnz     short loc_1400650FF
0x1400650fa  cmp     [rax+1Ch], bl
0x1400650fd  jz      short loc_140065105
0x1400650ff  lea     rcx, [rax+38h]
0x140065103  jmp     short loc_1400650E6
0x140065105  lea     r9, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006510c  xor     edx, edx
0x14006510e  lea     r8, [rsp+28h+arg_0]
0x140065113  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14006511a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140065121  nop     dword ptr [rax+rax+00h]
0x140065126  test    eax, eax
0x140065128  jz      short loc_140065133
0x14006512a  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, rbx
0x140065131  jmp     short loc_140065138
0x140065133  mov     ebx, 1
0x140065138  call    wil_details_RegisterFeatureUsageProvider
0x14006513d  test    eax, eax
0x14006513f  jz      short loc_14006514A
0x140065141  xor     ecx, ecx
0x140065143  test    ebx, ebx
0x140065145  cmovnz  eax, ecx
0x140065148  jmp     short loc_14006514C
0x14006514a  xor     eax, eax
0x14006514c  add     rsp, 20h
0x140065150  pop     rbx
0x140065151  retn
```
