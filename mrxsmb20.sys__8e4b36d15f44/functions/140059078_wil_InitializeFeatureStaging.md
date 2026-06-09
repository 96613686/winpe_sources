# wil_InitializeFeatureStaging

- ea: `0x140059078`
- end: `0x14005912f`
- name: `wil_InitializeFeatureStaging`
- size: `183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002bd4c`

## callees

- `0x14002c690`
- `0x14005215c`
- `0x1400523fc`
- `0x140059078`
- `0x140059138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400590a0`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400590a0`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400590f6`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x1400590f6`

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
  if ( WPP_MAIN_CB.ActiveThreadCount )
    return 0;
  v0 = 0;
  WPP_MAIN_CB.ActiveThreadCount = 1;
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
                           &WPP_MAIN_CB.Dpc.DpcData) )
        WPP_MAIN_CB.Dpc.DpcData = 0;
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
0x140059078  push    rbx
0x14005907a  sub     rsp, 20h
0x14005907e  cmp     cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x140059085  mov     [rsp+28h+arg_0], 0
0x14005908e  jnz     loc_140059126
0x140059094  xor     ebx, ebx
0x140059096  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 1
0x1400590a0  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400590a7  nop     dword ptr [rax+rax+00h]
0x1400590ac  mov     [rsp+28h+arg_0], rax
0x1400590b1  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400590b6  call    wil_details_EvaluateFeatureDependencies
0x1400590bb  lea     rcx, wil_details_featureDescriptors_a
0x1400590c2  call    wil_details_FeatureDescriptors_SkipPadding
0x1400590c7  test    rax, rax
0x1400590ca  jz      short loc_140059114
0x1400590cc  cmp     [rax+1Dh], bl
0x1400590cf  jnz     short loc_1400590DB
0x1400590d1  cmp     [rax+1Eh], bl
0x1400590d4  jnz     short loc_1400590DB
0x1400590d6  cmp     [rax+1Ch], bl
0x1400590d9  jz      short loc_1400590E1
0x1400590db  lea     rcx, [rax+38h]
0x1400590df  jmp     short loc_1400590C2
0x1400590e1  lea     r9, WPP_MAIN_CB.Dpc.DpcData
0x1400590e8  xor     edx, edx
0x1400590ea  lea     r8, [rsp+28h+arg_0]
0x1400590ef  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x1400590f6  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x1400590fd  nop     dword ptr [rax+rax+00h]
0x140059102  test    eax, eax
0x140059104  jz      short loc_14005910F
0x140059106  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rbx
0x14005910d  jmp     short loc_140059114
0x14005910f  mov     ebx, 1
0x140059114  call    wil_details_RegisterFeatureUsageProvider
0x140059119  test    eax, eax
0x14005911b  jz      short loc_140059126
0x14005911d  xor     ecx, ecx
0x14005911f  test    ebx, ebx
0x140059121  cmovnz  eax, ecx
0x140059124  jmp     short loc_140059128
0x140059126  xor     eax, eax
0x140059128  add     rsp, 20h
0x14005912c  pop     rbx
0x14005912d  retn
```
