# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(void)

- ea: `0x1800135d4`
- end: `0x1800136ad`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014f44`
- `0x1800172a4`

## callees

- `0x180013270`
- `0x1800135d4`
- `0x1800136b4`
- `0x1800155a0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Profile_Service_ETW_Logging__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Profile_Service_ETW_Logging__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Profile_Service_ETW_Logging__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Profile_Service_ETW_Logging__descriptor,
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
0x1800135d4  mov     [rsp+arg_10], rbx
0x1800135d9  mov     [rsp+arg_0], rcx
0x1800135de  push    rbp
0x1800135df  push    rsi
0x1800135e0  push    rdi
0x1800135e1  sub     rsp, 20h
0x1800135e5  mov     rsi, cs:Feature_Profile_Service_ETW_Logging__descriptor
0x1800135ec  mov     rdi, rdx
0x1800135ef  mov     qword ptr [rdx], 0
0x1800135f6  mov     eax, [rsi]
0x1800135f8  mov     [rdx], eax
0x1800135fa  and     eax, 6
0x1800135fd  cmp     al, 6
0x1800135ff  jz      loc_18001369D
0x180013605  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001360a  lea     r8, [rsp+38h+arg_0]
0x18001360f  mov     dword ptr [rsp+38h+arg_0], 0
0x180013617  lea     rdx, [rsp+38h+arg_8]
0x18001361c  mov     ebp, eax
0x18001361e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCurrentFeatureEnabledState(int *)
0x180013623  mov     eax, [rdi]
0x180013625  mov     rbx, [rsp+38h+arg_8]
0x18001362a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001362f  mov     edx, eax
0x180013631  mov     [rdi], eax
0x180013633  mov     ecx, eax
0x180013635  jz      short loc_180013650
0x180013637  test    dl, 2
0x18001363a  jnz     short loc_180013650
0x18001363c  and     ecx, 0FFFFF63Eh
0x180013642  mov     eax, ebx
0x180013644  and     eax, 9C1h
0x180013649  or      ecx, eax
0x18001364b  or      ecx, 2
0x18001364e  mov     [rdi], ecx
0x180013650  mov     r8d, edx
0x180013653  and     r8d, 4
0x180013657  jnz     short loc_18001366B
0x180013659  btr     ecx, 0Ah
0x18001365d  mov     eax, ebx
0x18001365f  and     eax, 400h
0x180013664  or      ecx, eax
0x180013666  or      ecx, 4
0x180013669  mov     [rdi], ecx
0x18001366b  mov     eax, edx
0x18001366d  lock cmpxchg [rsi], ecx
0x180013671  jnz     short loc_18001362A
0x180013673  test    r8d, r8d
0x180013676  jnz     short loc_180013688
0x180013678  mov     r8d, ebp
0x18001367b  mov     edx, 3
0x180013680  mov     rcx, rsi
0x180013683  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013688  mov     eax, [rdi]
0x18001368a  test    al, 2
0x18001368c  jnz     short loc_18001369D
0x18001368e  and     eax, 0FFFFF63Eh
0x180013693  and     ebx, 9C1h
0x180013699  or      eax, ebx
0x18001369b  mov     [rdi], eax
0x18001369d  mov     rbx, [rsp+38h+arg_10]
0x1800136a2  mov     rax, rdi
0x1800136a5  add     rsp, 20h
0x1800136a9  pop     rdi
0x1800136aa  pop     rsi
0x1800136ab  pop     rbp
0x1800136ac  retn
```
