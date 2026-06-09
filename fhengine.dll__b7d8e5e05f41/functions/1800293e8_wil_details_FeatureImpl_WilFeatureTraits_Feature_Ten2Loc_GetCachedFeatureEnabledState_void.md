# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x1800293e8`
- end: `0x1800294c1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c9ac`
- `0x18002e2e0`

## callees

- `0x180028ab4`
- `0x1800293e8`
- `0x180029c34`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Ten2Loc__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800293e8  mov     [rsp+arg_10], rbx
0x1800293ed  mov     [rsp+arg_0], rcx
0x1800293f2  push    rbp
0x1800293f3  push    rsi
0x1800293f4  push    rdi
0x1800293f5  sub     rsp, 20h
0x1800293f9  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180029400  mov     rdi, rdx
0x180029403  mov     qword ptr [rdx], 0
0x18002940a  mov     eax, [rsi]
0x18002940c  mov     [rdx], eax
0x18002940e  and     eax, 6
0x180029411  cmp     al, 6
0x180029413  jz      loc_1800294B1
0x180029419  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002941e  lea     r8, [rsp+38h+arg_0]
0x180029423  mov     dword ptr [rsp+38h+arg_0], 0
0x18002942b  lea     rdx, [rsp+38h+arg_8]
0x180029430  mov     ebp, eax
0x180029432  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180029437  mov     eax, [rdi]
0x180029439  mov     rbx, [rsp+38h+arg_8]
0x18002943e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180029443  mov     edx, eax
0x180029445  mov     [rdi], eax
0x180029447  mov     ecx, eax
0x180029449  jz      short loc_180029464
0x18002944b  test    dl, 2
0x18002944e  jnz     short loc_180029464
0x180029450  and     ecx, 0FFFFF63Eh
0x180029456  mov     eax, ebx
0x180029458  and     eax, 9C1h
0x18002945d  or      ecx, eax
0x18002945f  or      ecx, 2
0x180029462  mov     [rdi], ecx
0x180029464  mov     r8d, edx
0x180029467  and     r8d, 4
0x18002946b  jnz     short loc_18002947F
0x18002946d  btr     ecx, 0Ah
0x180029471  mov     eax, ebx
0x180029473  and     eax, 400h
0x180029478  or      ecx, eax
0x18002947a  or      ecx, 4
0x18002947d  mov     [rdi], ecx
0x18002947f  mov     eax, edx
0x180029481  lock cmpxchg [rsi], ecx
0x180029485  jnz     short loc_18002943E
0x180029487  test    r8d, r8d
0x18002948a  jnz     short loc_18002949C
0x18002948c  mov     r8d, ebp
0x18002948f  mov     edx, 3
0x180029494  mov     rcx, rsi
0x180029497  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002949c  mov     eax, [rdi]
0x18002949e  test    al, 2
0x1800294a0  jnz     short loc_1800294B1
0x1800294a2  and     eax, 0FFFFF63Eh
0x1800294a7  and     ebx, 9C1h
0x1800294ad  or      eax, ebx
0x1800294af  mov     [rdi], eax
0x1800294b1  mov     rbx, [rsp+38h+arg_10]
0x1800294b6  mov     rax, rdi
0x1800294b9  add     rsp, 20h
0x1800294bd  pop     rdi
0x1800294be  pop     rsi
0x1800294bf  pop     rbp
0x1800294c0  retn
```
