# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::GetCachedFeatureEnabledState(void)

- ea: `0x180026488`
- end: `0x180026561`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028c84`
- `0x1800290b8`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x180026488`
- `0x180027184`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_DirectCloudSync__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DirectCloudSync__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_DirectCloudSync__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_DirectCloudSync__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180026488  mov     [rsp+arg_10], rbx
0x18002648d  mov     [rsp+arg_0], rcx
0x180026492  push    rbp
0x180026493  push    rsi
0x180026494  push    rdi
0x180026495  sub     rsp, 20h
0x180026499  mov     rsi, cs:Feature_DirectCloudSync__descriptor
0x1800264a0  mov     rdi, rdx
0x1800264a3  mov     qword ptr [rdx], 0
0x1800264aa  mov     eax, [rsi]
0x1800264ac  mov     [rdx], eax
0x1800264ae  and     eax, 6
0x1800264b1  cmp     al, 6
0x1800264b3  jz      loc_180026551
0x1800264b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800264be  lea     r8, [rsp+38h+arg_0]
0x1800264c3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800264cb  lea     rdx, [rsp+38h+arg_8]
0x1800264d0  mov     ebp, eax
0x1800264d2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::GetCurrentFeatureEnabledState(int *)
0x1800264d7  mov     eax, [rdi]
0x1800264d9  mov     rbx, [rsp+38h+arg_8]
0x1800264de  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800264e3  mov     edx, eax
0x1800264e5  mov     [rdi], eax
0x1800264e7  mov     ecx, eax
0x1800264e9  jz      short loc_180026504
0x1800264eb  test    dl, 2
0x1800264ee  jnz     short loc_180026504
0x1800264f0  and     ecx, 0FFFFF63Eh
0x1800264f6  mov     eax, ebx
0x1800264f8  and     eax, 9C1h
0x1800264fd  or      ecx, eax
0x1800264ff  or      ecx, 2
0x180026502  mov     [rdi], ecx
0x180026504  mov     r8d, edx
0x180026507  and     r8d, 4
0x18002650b  jnz     short loc_18002651F
0x18002650d  btr     ecx, 0Ah
0x180026511  mov     eax, ebx
0x180026513  and     eax, 400h
0x180026518  or      ecx, eax
0x18002651a  or      ecx, 4
0x18002651d  mov     [rdi], ecx
0x18002651f  mov     eax, edx
0x180026521  lock cmpxchg [rsi], ecx
0x180026525  jnz     short loc_1800264DE
0x180026527  test    r8d, r8d
0x18002652a  jnz     short loc_18002653C
0x18002652c  mov     r8d, ebp
0x18002652f  mov     edx, 3
0x180026534  mov     rcx, rsi
0x180026537  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002653c  mov     eax, [rdi]
0x18002653e  test    al, 2
0x180026540  jnz     short loc_180026551
0x180026542  and     eax, 0FFFFF63Eh
0x180026547  and     ebx, 9C1h
0x18002654d  or      eax, ebx
0x18002654f  mov     [rdi], eax
0x180026551  mov     rbx, [rsp+38h+arg_10]
0x180026556  mov     rax, rdi
0x180026559  add     rsp, 20h
0x18002655d  pop     rdi
0x18002655e  pop     rsi
0x18002655f  pop     rbp
0x180026560  retn
```
