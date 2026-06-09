# wil_InitializeFeatureStaging

- ea: `0x1400373b4`
- end: `0x140037515`
- name: `wil_InitializeFeatureStaging`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140037080`

## callees

- `0x140033244`
- `0x1400373b4`
- `0x14003751c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400373e5`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x1400373e5`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003746a`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x14003746a`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400374de`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x1400374de`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  __int64 *v0; // rbx
  __int64 result; // rax
  __int128 v2; // [rsp+20h] [rbp-28h] BYREF
  __int64 v3; // [rsp+30h] [rbp-18h]

  if ( LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) )
    return 0;
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 1;
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
0x1400373b4  mov     [rsp+arg_8], rbx
0x1400373b9  mov     [rsp+arg_10], rbp
0x1400373be  push    rdi
0x1400373bf  sub     rsp, 40h
0x1400373c3  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x1400373ca  mov     [rsp+48h+arg_0], 0
0x1400373d3  jnz     loc_140037502
0x1400373d9  xor     edi, edi
0x1400373db  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 1
0x1400373e5  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x1400373ec  nop     dword ptr [rax+rax+00h]
0x1400373f1  mov     [rsp+48h+arg_0], rax
0x1400373f6  call    wil_details_PopulateInitialConfiguredFeatureStates
0x1400373fb  call    wil_details_EvaluateFeatureDependencies
0x140037400  lea     rbx, wil_details_featureDescriptors_a
0x140037407  lea     rbp, wil_details_featureDescriptors_a
0x14003740e  mov     rax, rbx
0x140037411  cmp     rbx, rbp
0x140037414  jnb     short loc_140037488
0x140037416  cmp     [rax], rdi
0x140037419  jnz     short loc_14003744E
0x14003741b  add     rax, 8
0x14003741f  cmp     rax, rbp
0x140037422  jb      short loc_140037416
0x140037424  jmp     short loc_140037488
0x140037426  cmp     [rax+1Dh], dil
0x14003742a  jnz     short loc_140037438
0x14003742c  cmp     [rax+1Eh], dil
0x140037430  jnz     short loc_140037438
0x140037432  cmp     [rax+1Ch], dil
0x140037436  jz      short loc_140037455
0x140037438  add     rax, 38h ; '8'
0x14003743c  jmp     short loc_140037447
0x14003743e  cmp     [rax], rdi
0x140037441  jnz     short loc_14003744E
0x140037443  add     rax, 8
0x140037447  cmp     rax, rbp
0x14003744a  jb      short loc_14003743E
0x14003744c  jmp     short loc_140037488
0x14003744e  test    rax, rax
0x140037451  jnz     short loc_140037426
0x140037453  jmp     short loc_140037488
0x140037455  lea     r9, WPP_MAIN_CB.Dpc.DeferredRoutine
0x14003745c  xor     edx, edx
0x14003745e  lea     r8, [rsp+48h+arg_0]
0x140037463  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x14003746a  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140037471  nop     dword ptr [rax+rax+00h]
0x140037476  test    eax, eax
0x140037478  jz      short loc_140037483
0x14003747a  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rdi
0x140037481  jmp     short loc_140037488
0x140037483  mov     edi, 1
0x140037488  xor     eax, eax
0x14003748a  xorps   xmm0, xmm0
0x14003748d  mov     [rsp+48h+var_18], rax
0x140037492  lea     rax, wil_details_RecordFeatureUsageReporting
0x140037499  movups  [rsp+48h+var_28], xmm0
0x14003749e  mov     cs:g_wil_details_recordFeatureUsage, rax
0x1400374a5  jmp     short loc_1400374B1
0x1400374a7  cmp     qword ptr [rbx], 0
0x1400374ab  jnz     short loc_1400374B8
0x1400374ad  add     rbx, 8
0x1400374b1  cmp     rbx, rbp
0x1400374b4  jb      short loc_1400374A7
0x1400374b6  xor     ebx, ebx
0x1400374b8  lea     r8, g_wil_details_featureUsageProvider
0x1400374bf  mov     qword ptr [rsp+48h+var_28], rbx
0x1400374c4  lea     rdx, [rsp+48h+var_28]
0x1400374c9  mov     qword ptr [rsp+48h+var_28+8], rbp
0x1400374ce  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x1400374d5  mov     [rsp+48h+var_18], 0
0x1400374de  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x1400374e5  nop     dword ptr [rax+rax+00h]
0x1400374ea  test    eax, eax
0x1400374ec  jz      short loc_140037502
0x1400374ee  xor     ecx, ecx
0x1400374f0  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400374fb  test    edi, edi
0x1400374fd  cmovnz  eax, ecx
0x140037500  jmp     short loc_140037504
0x140037502  xor     eax, eax
0x140037504  mov     rbx, [rsp+48h+arg_8]
0x140037509  mov     rbp, [rsp+48h+arg_10]
0x14003750e  add     rsp, 40h
0x140037512  pop     rdi
0x140037513  retn
```
