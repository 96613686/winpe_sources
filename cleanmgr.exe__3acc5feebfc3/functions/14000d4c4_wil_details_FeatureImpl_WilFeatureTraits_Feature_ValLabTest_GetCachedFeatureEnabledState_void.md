# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x14000d4c4`
- end: `0x14000d59d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ea24`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000d4c4`
- `0x14000dd68`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000d4c4  mov     [rsp+arg_10], rbx
0x14000d4c9  mov     [rsp+arg_0], rcx
0x14000d4ce  push    rbp
0x14000d4cf  push    rsi
0x14000d4d0  push    rdi
0x14000d4d1  sub     rsp, 20h
0x14000d4d5  mov     rsi, cs:Feature_ValLabTest__descriptor
0x14000d4dc  mov     rdi, rdx
0x14000d4df  mov     qword ptr [rdx], 0
0x14000d4e6  mov     eax, [rsi]
0x14000d4e8  mov     [rdx], eax
0x14000d4ea  and     eax, 6
0x14000d4ed  cmp     al, 6
0x14000d4ef  jz      loc_14000D58D
0x14000d4f5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000d4fa  lea     r8, [rsp+38h+arg_0]
0x14000d4ff  mov     dword ptr [rsp+38h+arg_0], 0
0x14000d507  lea     rdx, [rsp+38h+arg_8]
0x14000d50c  mov     ebp, eax
0x14000d50e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x14000d513  mov     eax, [rdi]
0x14000d515  mov     rbx, [rsp+38h+arg_8]
0x14000d51a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000d51f  mov     edx, eax
0x14000d521  mov     [rdi], eax
0x14000d523  mov     ecx, eax
0x14000d525  jz      short loc_14000D540
0x14000d527  test    dl, 2
0x14000d52a  jnz     short loc_14000D540
0x14000d52c  and     ecx, 0FFFFF63Eh
0x14000d532  mov     eax, ebx
0x14000d534  and     eax, 9C1h
0x14000d539  or      ecx, eax
0x14000d53b  or      ecx, 2
0x14000d53e  mov     [rdi], ecx
0x14000d540  mov     r8d, edx
0x14000d543  and     r8d, 4
0x14000d547  jnz     short loc_14000D55B
0x14000d549  btr     ecx, 0Ah
0x14000d54d  mov     eax, ebx
0x14000d54f  and     eax, 400h
0x14000d554  or      ecx, eax
0x14000d556  or      ecx, 4
0x14000d559  mov     [rdi], ecx
0x14000d55b  mov     eax, edx
0x14000d55d  lock cmpxchg [rsi], ecx
0x14000d561  jnz     short loc_14000D51A
0x14000d563  test    r8d, r8d
0x14000d566  jnz     short loc_14000D578
0x14000d568  mov     r8d, ebp
0x14000d56b  mov     edx, 3
0x14000d570  mov     rcx, rsi
0x14000d573  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000d578  mov     eax, [rdi]
0x14000d57a  test    al, 2
0x14000d57c  jnz     short loc_14000D58D
0x14000d57e  and     eax, 0FFFFF63Eh
0x14000d583  and     ebx, 9C1h
0x14000d589  or      eax, ebx
0x14000d58b  mov     [rdi], eax
0x14000d58d  mov     rbx, [rsp+38h+arg_10]
0x14000d592  mov     rax, rdi
0x14000d595  add     rsp, 20h
0x14000d599  pop     rdi
0x14000d59a  pop     rsi
0x14000d59b  pop     rbp
0x14000d59c  retn
```
