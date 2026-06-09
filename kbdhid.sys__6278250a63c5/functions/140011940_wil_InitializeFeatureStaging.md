# wil_InitializeFeatureStaging

- ea: `0x140011940`
- end: `0x140011ac3`
- name: `wil_InitializeFeatureStaging`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140011168`

## callees

- `0x14000f010`
- `0x140011010`
- `0x140011940`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140011973`
- `ntoskrnl!RtlQueryFeatureConfigurationChangeStamp` at `0x140011973`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140011a0c`
- `ntoskrnl!RtlRegisterFeatureConfigurationChangeNotification` at `0x140011a0c`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140011a83`
- `ntoskrnl!RtlRegisterFeatureUsageProvider` at `0x140011a83`

## pseudocode

```c
__int64 wil_InitializeFeatureStaging()
{
  int v0; // edi
  _QWORD *v1; // rbx
  _UNKNOWN **v2; // rax
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = 0;
  if ( LODWORD(WPP_MAIN_CB.SecurityDescriptor) )
    return 0;
  v0 = 0;
  LODWORD(WPP_MAIN_CB.SecurityDescriptor) = 1;
  v6 = RtlQueryFeatureConfigurationChangeStamp();
  wil_details_PopulateInitialConfiguredFeatureStates();
  wil_details_EvaluateFeatureDependencies();
  v1 = &wil_details_featureDescriptors_a;
  v2 = &wil_details_featureDescriptors_a;
  if ( &wil_details_featureDescriptors_a < (_UNKNOWN **)wil_details_featureDescriptors_z )
  {
    while ( !*v2 )
    {
      if ( ++v2 >= (_UNKNOWN **)wil_details_featureDescriptors_z )
        goto LABEL_19;
    }
    if ( v2 )
    {
      while ( *((_BYTE *)v2 + 29) || *((_BYTE *)v2 + 30) || *((_BYTE *)v2 + 28) )
      {
        v2 += 7;
        if ( v2 < (_UNKNOWN **)wil_details_featureDescriptors_z )
        {
          while ( !*v2 )
          {
            if ( ++v2 >= (_UNKNOWN **)wil_details_featureDescriptors_z )
              goto LABEL_19;
          }
          if ( v2 )
            continue;
        }
        goto LABEL_19;
      }
      if ( (unsigned int)RtlRegisterFeatureConfigurationChangeNotification(
                           wil_details_ReevaluateOnFeatureConfigurationChange,
                           0,
                           &v6,
                           &WPP_MAIN_CB.Dpc.DpcData) )
        WPP_MAIN_CB.Dpc.DpcData = 0;
      else
        v0 = 1;
    }
  }
LABEL_19:
  v5 = 0;
  v4 = 0;
  g_wil_details_recordFeatureUsage = (__int64)wil_details_RecordFeatureUsageReporting;
  if ( &wil_details_featureDescriptors_a >= (_UNKNOWN **)wil_details_featureDescriptors_z )
  {
LABEL_22:
    v1 = 0;
  }
  else
  {
    while ( !*v1 )
    {
      if ( ++v1 >= wil_details_featureDescriptors_z )
        goto LABEL_22;
    }
  }
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
0x140011940  mov     [rsp+arg_18], rbp
0x140011945  push    rdi
0x140011946  sub     rsp, 40h
0x14001194a  xor     ebp, ebp
0x14001194c  cmp     dword ptr cs:WPP_MAIN_CB.SecurityDescriptor, ebp
0x140011952  mov     [rsp+48h+arg_0], rbp
0x140011957  jnz     loc_140011AB5
0x14001195d  mov     [rsp+48h+arg_8], rbx
0x140011962  mov     edi, ebp
0x140011964  mov     [rsp+48h+arg_10], rsi
0x140011969  mov     dword ptr cs:WPP_MAIN_CB.SecurityDescriptor, 1
0x140011973  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x14001197a  nop     dword ptr [rax+rax+00h]
0x14001197f  mov     [rsp+48h+arg_0], rax
0x140011984  call    wil_details_PopulateInitialConfiguredFeatureStates
0x140011989  call    wil_details_EvaluateFeatureDependencies
0x14001198e  lea     rbx, wil_details_featureDescriptors_a
0x140011995  lea     rsi, wil_details_featureDescriptors_z
0x14001199c  mov     rax, rbx
0x14001199f  cmp     rbx, rsi
0x1400119a2  jnb     loc_140011A2A
0x1400119a8  cmp     [rax], rdi
0x1400119ab  jnz     short loc_1400119B8
0x1400119ad  add     rax, 8
0x1400119b1  cmp     rax, rsi
0x1400119b4  jb      short loc_1400119A8
0x1400119b6  jmp     short loc_140011A2A
0x1400119b8  test    rax, rax
0x1400119bb  jz      short loc_140011A2A
0x1400119bd  nop     dword ptr [rax]
0x1400119c0  cmp     [rax+1Dh], dil
0x1400119c4  jnz     short loc_1400119D2
0x1400119c6  cmp     [rax+1Eh], dil
0x1400119ca  jnz     short loc_1400119D2
0x1400119cc  cmp     [rax+1Ch], dil
0x1400119d0  jz      short loc_1400119F7
0x1400119d2  add     rax, 38h ; '8'
0x1400119d6  cmp     rax, rsi
0x1400119d9  jnb     short loc_140011A2A
0x1400119db  nop     dword ptr [rax+rax+00h]
0x1400119e0  cmp     [rax], rdi
0x1400119e3  jnz     short loc_1400119F0
0x1400119e5  add     rax, 8
0x1400119e9  cmp     rax, rsi
0x1400119ec  jb      short loc_1400119E0
0x1400119ee  jmp     short loc_140011A2A
0x1400119f0  test    rax, rax
0x1400119f3  jnz     short loc_1400119C0
0x1400119f5  jmp     short loc_140011A2A
0x1400119f7  lea     r9, WPP_MAIN_CB.Dpc.DpcData
0x1400119fe  xor     edx, edx
0x140011a00  lea     r8, [rsp+48h+arg_0]
0x140011a05  lea     rcx, wil_details_ReevaluateOnFeatureConfigurationChange
0x140011a0c  call    cs:__imp_RtlRegisterFeatureConfigurationChangeNotification
0x140011a13  nop     dword ptr [rax+rax+00h]
0x140011a18  test    eax, eax
0x140011a1a  jz      short loc_140011A25
0x140011a1c  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rbp
0x140011a23  jmp     short loc_140011A2A
0x140011a25  mov     edi, 1
0x140011a2a  xor     eax, eax
0x140011a2c  xorps   xmm0, xmm0
0x140011a2f  mov     [rsp+48h+var_18], rax
0x140011a34  lea     rax, wil_details_RecordFeatureUsageReporting
0x140011a3b  movups  [rsp+48h+var_28], xmm0
0x140011a40  mov     cs:g_wil_details_recordFeatureUsage, rax
0x140011a47  cmp     rbx, rsi
0x140011a4a  jnb     short loc_140011A5E
0x140011a4c  nop     dword ptr [rax+00h]
0x140011a50  cmp     [rbx], rbp
0x140011a53  jnz     short loc_140011A61
0x140011a55  add     rbx, 8
0x140011a59  cmp     rbx, rsi
0x140011a5c  jb      short loc_140011A50
0x140011a5e  mov     rbx, rbp
0x140011a61  lea     r8, g_wil_details_featureUsageProvider
0x140011a68  mov     qword ptr [rsp+48h+var_28], rbx
0x140011a6d  lea     rdx, [rsp+48h+var_28]
0x140011a72  mov     qword ptr [rsp+48h+var_28+8], rsi
0x140011a77  lea     rcx, wil_details_OnFeatureUsageProviderFlushNotification
0x140011a7e  mov     [rsp+48h+var_18], rbp
0x140011a83  call    cs:__imp_RtlRegisterFeatureUsageProvider
0x140011a8a  nop     dword ptr [rax+rax+00h]
0x140011a8f  mov     rsi, [rsp+48h+arg_10]
0x140011a94  mov     rbx, [rsp+48h+arg_8]
0x140011a99  test    eax, eax
0x140011a9b  jz      short loc_140011AB5
0x140011a9d  test    edi, edi
0x140011a9f  mov     cs:g_wil_details_featureUsageProvider, rbp
0x140011aa6  cmovnz  eax, ebp
0x140011aa9  mov     rbp, [rsp+48h+arg_18]
0x140011aae  add     rsp, 40h
0x140011ab2  pop     rdi
0x140011ab3  retn
0x140011ab5  mov     rbp, [rsp+48h+arg_18]
0x140011aba  xor     eax, eax
0x140011abc  add     rsp, 40h
0x140011ac0  pop     rdi
0x140011ac1  retn
```
