# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCachedFeatureEnabledState(void)

- ea: `0x180005fc4`
- end: `0x18000609d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c5f4`

## callees

- `0x1800058f8`
- `0x180005fc4`
- `0x180006520`
- `0x18000b7c8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_HotpatchMonitoring_Service__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (__int64 *)Feature_Servicing_HotpatchMonitoring_Service__descriptor,
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
0x180005fc4  mov     [rsp+arg_10], rbx
0x180005fc9  mov     [rsp+arg_0], rcx
0x180005fce  push    rbp
0x180005fcf  push    rsi
0x180005fd0  push    rdi
0x180005fd1  sub     rsp, 20h
0x180005fd5  mov     rsi, cs:Feature_Servicing_HotpatchMonitoring_Service__descriptor
0x180005fdc  mov     rdi, rdx
0x180005fdf  mov     qword ptr [rdx], 0
0x180005fe6  mov     eax, [rsi]
0x180005fe8  mov     [rdx], eax
0x180005fea  and     eax, 6
0x180005fed  cmp     al, 6
0x180005fef  jz      loc_18000608D
0x180005ff5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005ffa  lea     r8, [rsp+38h+arg_0]
0x180005fff  mov     dword ptr [rsp+38h+arg_0], 0
0x180006007  lea     rdx, [rsp+38h+arg_8]
0x18000600c  mov     ebp, eax
0x18000600e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCurrentFeatureEnabledState(int *)
0x180006013  mov     eax, [rdi]
0x180006015  mov     rbx, [rsp+38h+arg_8]
0x18000601a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000601f  mov     edx, eax
0x180006021  mov     [rdi], eax
0x180006023  mov     ecx, eax
0x180006025  jz      short loc_180006040
0x180006027  test    dl, 2
0x18000602a  jnz     short loc_180006040
0x18000602c  and     ecx, 0FFFFF63Eh
0x180006032  mov     eax, ebx
0x180006034  and     eax, 9C1h
0x180006039  or      ecx, eax
0x18000603b  or      ecx, 2
0x18000603e  mov     [rdi], ecx
0x180006040  mov     r8d, edx
0x180006043  and     r8d, 4
0x180006047  jnz     short loc_18000605B
0x180006049  btr     ecx, 0Ah
0x18000604d  mov     eax, ebx
0x18000604f  and     eax, 400h
0x180006054  or      ecx, eax
0x180006056  or      ecx, 4
0x180006059  mov     [rdi], ecx
0x18000605b  mov     eax, edx
0x18000605d  lock cmpxchg [rsi], ecx
0x180006061  jnz     short loc_18000601A
0x180006063  test    r8d, r8d
0x180006066  jnz     short loc_180006078
0x180006068  mov     r8d, ebp
0x18000606b  mov     edx, 3
0x180006070  mov     rcx, rsi
0x180006073  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006078  mov     eax, [rdi]
0x18000607a  test    al, 2
0x18000607c  jnz     short loc_18000608D
0x18000607e  and     eax, 0FFFFF63Eh
0x180006083  and     ebx, 9C1h
0x180006089  or      eax, ebx
0x18000608b  mov     [rdi], eax
0x18000608d  mov     rbx, [rsp+38h+arg_10]
0x180006092  mov     rax, rdi
0x180006095  add     rsp, 20h
0x180006099  pop     rdi
0x18000609a  pop     rsi
0x18000609b  pop     rbp
0x18000609c  retn
```
