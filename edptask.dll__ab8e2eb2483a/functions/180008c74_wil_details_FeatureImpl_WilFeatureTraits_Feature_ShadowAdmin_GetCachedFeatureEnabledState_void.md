# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCachedFeatureEnabledState(void)

- ea: `0x180008c74`
- end: `0x180008d4d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012090`

## callees

- `0x1800084b4`
- `0x180008c74`
- `0x180009830`
- `0x1800113c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ShadowAdmin__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ShadowAdmin__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ShadowAdmin__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ShadowAdmin__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180008c74  mov     [rsp+arg_10], rbx
0x180008c79  mov     [rsp+arg_0], rcx
0x180008c7e  push    rbp
0x180008c7f  push    rsi
0x180008c80  push    rdi
0x180008c81  sub     rsp, 20h
0x180008c85  mov     rsi, cs:Feature_ShadowAdmin__descriptor
0x180008c8c  mov     rdi, rdx
0x180008c8f  mov     qword ptr [rdx], 0
0x180008c96  mov     eax, [rsi]
0x180008c98  mov     [rdx], eax
0x180008c9a  and     eax, 6
0x180008c9d  cmp     al, 6
0x180008c9f  jz      loc_180008D3D
0x180008ca5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008caa  lea     r8, [rsp+38h+arg_0]
0x180008caf  mov     dword ptr [rsp+38h+arg_0], 0
0x180008cb7  lea     rdx, [rsp+38h+arg_8]
0x180008cbc  mov     ebp, eax
0x180008cbe  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCurrentFeatureEnabledState(int *)
0x180008cc3  mov     eax, [rdi]
0x180008cc5  mov     rbx, [rsp+38h+arg_8]
0x180008cca  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008ccf  mov     edx, eax
0x180008cd1  mov     [rdi], eax
0x180008cd3  mov     ecx, eax
0x180008cd5  jz      short loc_180008CF0
0x180008cd7  test    dl, 2
0x180008cda  jnz     short loc_180008CF0
0x180008cdc  and     ecx, 0FFFFF63Eh
0x180008ce2  mov     eax, ebx
0x180008ce4  and     eax, 9C1h
0x180008ce9  or      ecx, eax
0x180008ceb  or      ecx, 2
0x180008cee  mov     [rdi], ecx
0x180008cf0  mov     r8d, edx
0x180008cf3  and     r8d, 4
0x180008cf7  jnz     short loc_180008D0B
0x180008cf9  btr     ecx, 0Ah
0x180008cfd  mov     eax, ebx
0x180008cff  and     eax, 400h
0x180008d04  or      ecx, eax
0x180008d06  or      ecx, 4
0x180008d09  mov     [rdi], ecx
0x180008d0b  mov     eax, edx
0x180008d0d  lock cmpxchg [rsi], ecx
0x180008d11  jnz     short loc_180008CCA
0x180008d13  test    r8d, r8d
0x180008d16  jnz     short loc_180008D28
0x180008d18  mov     r8d, ebp
0x180008d1b  mov     edx, 3
0x180008d20  mov     rcx, rsi
0x180008d23  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008d28  mov     eax, [rdi]
0x180008d2a  test    al, 2
0x180008d2c  jnz     short loc_180008D3D
0x180008d2e  and     eax, 0FFFFF63Eh
0x180008d33  and     ebx, 9C1h
0x180008d39  or      eax, ebx
0x180008d3b  mov     [rdi], eax
0x180008d3d  mov     rbx, [rsp+38h+arg_10]
0x180008d42  mov     rax, rdi
0x180008d45  add     rsp, 20h
0x180008d49  pop     rdi
0x180008d4a  pop     rsi
0x180008d4b  pop     rbp
0x180008d4c  retn
```
