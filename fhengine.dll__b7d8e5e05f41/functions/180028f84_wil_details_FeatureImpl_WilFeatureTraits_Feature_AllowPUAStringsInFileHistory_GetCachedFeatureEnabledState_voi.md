# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::GetCachedFeatureEnabledState(void)

- ea: `0x180028f84`
- end: `0x180029062`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `222`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c710`
- `0x18002e2a4`

## callees

- `0x180028ab4`
- `0x180028f84`
- `0x18002997c`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::GetCachedFeatureEnabledState(
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
  int v12; // r8d
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_AllowPUAStringsInFileHistory__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AllowPUAStringsInFileHistory__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      &v14);
    if ( !v5 )
      LODWORD(v14) = 0;
    v7 = *(_DWORD *)a2;
    v8 = v15;
    do
    {
      v9 = (_DWORD)v14 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_AllowPUAStringsInFileHistory__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_AllowPUAStringsInFileHistory__descriptor,
        0,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180028f84  mov     [rsp+arg_10], rbx
0x180028f89  mov     [rsp+arg_0], rcx
0x180028f8e  push    rbp
0x180028f8f  push    rsi
0x180028f90  push    rdi
0x180028f91  sub     rsp, 20h
0x180028f95  mov     rsi, cs:Feature_AllowPUAStringsInFileHistory__descriptor
0x180028f9c  mov     rdi, rdx
0x180028f9f  mov     qword ptr [rdx], 0
0x180028fa6  mov     eax, [rsi]
0x180028fa8  mov     [rdx], eax
0x180028faa  and     eax, 6
0x180028fad  cmp     al, 6
0x180028faf  jz      loc_180029052
0x180028fb5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180028fba  lea     r8, [rsp+38h+arg_0]
0x180028fbf  mov     dword ptr [rsp+38h+arg_0], 0
0x180028fc7  lea     rdx, [rsp+38h+arg_8]
0x180028fcc  mov     ebp, eax
0x180028fce  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::GetCurrentFeatureEnabledState(int *)
0x180028fd3  test    ebp, ebp
0x180028fd5  jnz     short loc_180028FDB
0x180028fd7  mov     dword ptr [rsp+38h+arg_0], ebp
0x180028fdb  mov     eax, [rdi]
0x180028fdd  mov     rbx, [rsp+38h+arg_8]
0x180028fe2  cmp     dword ptr [rsp+38h+arg_0], 0
0x180028fe7  mov     edx, eax
0x180028fe9  mov     [rdi], eax
0x180028feb  mov     ecx, eax
0x180028fed  jz      short loc_180029008
0x180028fef  test    dl, 2
0x180028ff2  jnz     short loc_180029008
0x180028ff4  and     ecx, 0FFFFF63Eh
0x180028ffa  mov     eax, ebx
0x180028ffc  and     eax, 9C1h
0x180029001  or      ecx, eax
0x180029003  or      ecx, 2
0x180029006  mov     [rdi], ecx
0x180029008  mov     r8d, edx
0x18002900b  and     r8d, 4
0x18002900f  jnz     short loc_180029023
0x180029011  btr     ecx, 0Ah
0x180029015  mov     eax, ebx
0x180029017  and     eax, 400h
0x18002901c  or      ecx, eax
0x18002901e  or      ecx, 4
0x180029021  mov     [rdi], ecx
0x180029023  mov     eax, edx
0x180029025  lock cmpxchg [rsi], ecx
0x180029029  jnz     short loc_180028FE2
0x18002902b  test    r8d, r8d
0x18002902e  jnz     short loc_18002903D
0x180029030  mov     r8d, ebp
0x180029033  xor     edx, edx
0x180029035  mov     rcx, rsi
0x180029038  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002903d  mov     eax, [rdi]
0x18002903f  test    al, 2
0x180029041  jnz     short loc_180029052
0x180029043  and     eax, 0FFFFF63Eh
0x180029048  and     ebx, 9C1h
0x18002904e  or      eax, ebx
0x180029050  mov     [rdi], eax
0x180029052  mov     rbx, [rsp+38h+arg_10]
0x180029057  mov     rax, rdi
0x18002905a  add     rsp, 20h
0x18002905e  pop     rdi
0x18002905f  pop     rsi
0x180029060  pop     rbp
0x180029061  retn
```
