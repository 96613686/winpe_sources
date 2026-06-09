# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180026d88`
- end: `0x180026e61`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028ea4`
- `0x1800291a8`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x180026d88`
- `0x18002764c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180026d88  mov     [rsp+arg_10], rbx
0x180026d8d  mov     [rsp+arg_0], rcx
0x180026d92  push    rbp
0x180026d93  push    rsi
0x180026d94  push    rdi
0x180026d95  sub     rsp, 20h
0x180026d99  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180026da0  mov     rdi, rdx
0x180026da3  mov     qword ptr [rdx], 0
0x180026daa  mov     eax, [rsi]
0x180026dac  mov     [rdx], eax
0x180026dae  and     eax, 6
0x180026db1  cmp     al, 6
0x180026db3  jz      loc_180026E51
0x180026db9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026dbe  lea     r8, [rsp+38h+arg_0]
0x180026dc3  mov     dword ptr [rsp+38h+arg_0], 0
0x180026dcb  lea     rdx, [rsp+38h+arg_8]
0x180026dd0  mov     ebp, eax
0x180026dd2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180026dd7  mov     eax, [rdi]
0x180026dd9  mov     rbx, [rsp+38h+arg_8]
0x180026dde  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026de3  mov     edx, eax
0x180026de5  mov     [rdi], eax
0x180026de7  mov     ecx, eax
0x180026de9  jz      short loc_180026E04
0x180026deb  test    dl, 2
0x180026dee  jnz     short loc_180026E04
0x180026df0  and     ecx, 0FFFFF63Eh
0x180026df6  mov     eax, ebx
0x180026df8  and     eax, 9C1h
0x180026dfd  or      ecx, eax
0x180026dff  or      ecx, 2
0x180026e02  mov     [rdi], ecx
0x180026e04  mov     r8d, edx
0x180026e07  and     r8d, 4
0x180026e0b  jnz     short loc_180026E1F
0x180026e0d  btr     ecx, 0Ah
0x180026e11  mov     eax, ebx
0x180026e13  and     eax, 400h
0x180026e18  or      ecx, eax
0x180026e1a  or      ecx, 4
0x180026e1d  mov     [rdi], ecx
0x180026e1f  mov     eax, edx
0x180026e21  lock cmpxchg [rsi], ecx
0x180026e25  jnz     short loc_180026DDE
0x180026e27  test    r8d, r8d
0x180026e2a  jnz     short loc_180026E3C
0x180026e2c  mov     r8d, ebp
0x180026e2f  mov     edx, 3
0x180026e34  mov     rcx, rsi
0x180026e37  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180026e3c  mov     eax, [rdi]
0x180026e3e  test    al, 2
0x180026e40  jnz     short loc_180026E51
0x180026e42  and     eax, 0FFFFF63Eh
0x180026e47  and     ebx, 9C1h
0x180026e4d  or      eax, ebx
0x180026e4f  mov     [rdi], eax
0x180026e51  mov     rbx, [rsp+38h+arg_10]
0x180026e56  mov     rax, rdi
0x180026e59  add     rsp, 20h
0x180026e5d  pop     rdi
0x180026e5e  pop     rsi
0x180026e5f  pop     rbp
0x180026e60  retn
```
