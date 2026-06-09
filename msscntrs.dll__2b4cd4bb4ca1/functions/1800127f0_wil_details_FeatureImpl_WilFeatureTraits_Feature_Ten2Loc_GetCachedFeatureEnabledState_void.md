# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x1800127f0`
- end: `0x1800128c9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800136dc`

## callees

- `0x180005c18`
- `0x180009714`
- `0x1800127f0`
- `0x180012dd0`

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
0x1800127f0  mov     [rsp+arg_10], rbx
0x1800127f5  mov     [rsp+arg_0], rcx
0x1800127fa  push    rbp
0x1800127fb  push    rsi
0x1800127fc  push    rdi
0x1800127fd  sub     rsp, 20h
0x180012801  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180012808  mov     rdi, rdx
0x18001280b  mov     qword ptr [rdx], 0
0x180012812  mov     eax, [rsi]
0x180012814  mov     [rdx], eax
0x180012816  and     eax, 6
0x180012819  cmp     al, 6
0x18001281b  jz      loc_1800128B9
0x180012821  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012826  lea     r8, [rsp+38h+arg_0]
0x18001282b  mov     dword ptr [rsp+38h+arg_0], 0
0x180012833  lea     rdx, [rsp+38h+arg_8]
0x180012838  mov     ebp, eax
0x18001283a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18001283f  mov     eax, [rdi]
0x180012841  mov     rbx, [rsp+38h+arg_8]
0x180012846  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001284b  mov     edx, eax
0x18001284d  mov     [rdi], eax
0x18001284f  mov     ecx, eax
0x180012851  jz      short loc_18001286C
0x180012853  test    dl, 2
0x180012856  jnz     short loc_18001286C
0x180012858  and     ecx, 0FFFFF63Eh
0x18001285e  mov     eax, ebx
0x180012860  and     eax, 9C1h
0x180012865  or      ecx, eax
0x180012867  or      ecx, 2
0x18001286a  mov     [rdi], ecx
0x18001286c  mov     r8d, edx
0x18001286f  and     r8d, 4
0x180012873  jnz     short loc_180012887
0x180012875  btr     ecx, 0Ah
0x180012879  mov     eax, ebx
0x18001287b  and     eax, 400h
0x180012880  or      ecx, eax
0x180012882  or      ecx, 4
0x180012885  mov     [rdi], ecx
0x180012887  mov     eax, edx
0x180012889  lock cmpxchg [rsi], ecx
0x18001288d  jnz     short loc_180012846
0x18001288f  test    r8d, r8d
0x180012892  jnz     short loc_1800128A4
0x180012894  mov     r8d, ebp
0x180012897  mov     edx, 3
0x18001289c  mov     rcx, rsi
0x18001289f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800128a4  mov     eax, [rdi]
0x1800128a6  test    al, 2
0x1800128a8  jnz     short loc_1800128B9
0x1800128aa  and     eax, 0FFFFF63Eh
0x1800128af  and     ebx, 9C1h
0x1800128b5  or      eax, ebx
0x1800128b7  mov     [rdi], eax
0x1800128b9  mov     rbx, [rsp+38h+arg_10]
0x1800128be  mov     rax, rdi
0x1800128c1  add     rsp, 20h
0x1800128c5  pop     rdi
0x1800128c6  pop     rsi
0x1800128c7  pop     rbp
0x1800128c8  retn
```
