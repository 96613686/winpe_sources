# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCachedFeatureEnabledState(void)

- ea: `0x1800060a4`
- end: `0x18000617d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c694`

## callees

- `0x1800058f8`
- `0x1800060a4`
- `0x180006668`
- `0x18000b7c8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800060a4  mov     [rsp+arg_10], rbx
0x1800060a9  mov     [rsp+arg_0], rcx
0x1800060ae  push    rbp
0x1800060af  push    rsi
0x1800060b0  push    rdi
0x1800060b1  sub     rsp, 20h
0x1800060b5  mov     rsi, cs:Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor
0x1800060bc  mov     rdi, rdx
0x1800060bf  mov     qword ptr [rdx], 0
0x1800060c6  mov     eax, [rsi]
0x1800060c8  mov     [rdx], eax
0x1800060ca  and     eax, 6
0x1800060cd  cmp     al, 6
0x1800060cf  jz      loc_18000616D
0x1800060d5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800060da  lea     r8, [rsp+38h+arg_0]
0x1800060df  mov     dword ptr [rsp+38h+arg_0], 0
0x1800060e7  lea     rdx, [rsp+38h+arg_8]
0x1800060ec  mov     ebp, eax
0x1800060ee  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCurrentFeatureEnabledState(int *)
0x1800060f3  mov     eax, [rdi]
0x1800060f5  mov     rbx, [rsp+38h+arg_8]
0x1800060fa  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800060ff  mov     edx, eax
0x180006101  mov     [rdi], eax
0x180006103  mov     ecx, eax
0x180006105  jz      short loc_180006120
0x180006107  test    dl, 2
0x18000610a  jnz     short loc_180006120
0x18000610c  and     ecx, 0FFFFF63Eh
0x180006112  mov     eax, ebx
0x180006114  and     eax, 9C1h
0x180006119  or      ecx, eax
0x18000611b  or      ecx, 2
0x18000611e  mov     [rdi], ecx
0x180006120  mov     r8d, edx
0x180006123  and     r8d, 4
0x180006127  jnz     short loc_18000613B
0x180006129  btr     ecx, 0Ah
0x18000612d  mov     eax, ebx
0x18000612f  and     eax, 400h
0x180006134  or      ecx, eax
0x180006136  or      ecx, 4
0x180006139  mov     [rdi], ecx
0x18000613b  mov     eax, edx
0x18000613d  lock cmpxchg [rsi], ecx
0x180006141  jnz     short loc_1800060FA
0x180006143  test    r8d, r8d
0x180006146  jnz     short loc_180006158
0x180006148  mov     r8d, ebp
0x18000614b  mov     edx, 3
0x180006150  mov     rcx, rsi
0x180006153  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006158  mov     eax, [rdi]
0x18000615a  test    al, 2
0x18000615c  jnz     short loc_18000616D
0x18000615e  and     eax, 0FFFFF63Eh
0x180006163  and     ebx, 9C1h
0x180006169  or      eax, ebx
0x18000616b  mov     [rdi], eax
0x18000616d  mov     rbx, [rsp+38h+arg_10]
0x180006172  mov     rax, rdi
0x180006175  add     rsp, 20h
0x180006179  pop     rdi
0x18000617a  pop     rsi
0x18000617b  pop     rbp
0x18000617c  retn
```
