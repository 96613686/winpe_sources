# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180029148`
- end: `0x180029221`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c820`

## callees

- `0x180028ab4`
- `0x180029148`
- `0x180029ac0`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180029148  mov     [rsp+arg_10], rbx
0x18002914d  mov     [rsp+arg_0], rcx
0x180029152  push    rbp
0x180029153  push    rsi
0x180029154  push    rdi
0x180029155  sub     rsp, 20h
0x180029159  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180029160  mov     rdi, rdx
0x180029163  mov     qword ptr [rdx], 0
0x18002916a  mov     eax, [rsi]
0x18002916c  mov     [rdx], eax
0x18002916e  and     eax, 6
0x180029171  cmp     al, 6
0x180029173  jz      loc_180029211
0x180029179  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002917e  lea     r8, [rsp+38h+arg_0]
0x180029183  mov     dword ptr [rsp+38h+arg_0], 0
0x18002918b  lea     rdx, [rsp+38h+arg_8]
0x180029190  mov     ebp, eax
0x180029192  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180029197  mov     eax, [rdi]
0x180029199  mov     rbx, [rsp+38h+arg_8]
0x18002919e  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800291a3  mov     edx, eax
0x1800291a5  mov     [rdi], eax
0x1800291a7  mov     ecx, eax
0x1800291a9  jz      short loc_1800291C4
0x1800291ab  test    dl, 2
0x1800291ae  jnz     short loc_1800291C4
0x1800291b0  and     ecx, 0FFFFF63Eh
0x1800291b6  mov     eax, ebx
0x1800291b8  and     eax, 9C1h
0x1800291bd  or      ecx, eax
0x1800291bf  or      ecx, 2
0x1800291c2  mov     [rdi], ecx
0x1800291c4  mov     r8d, edx
0x1800291c7  and     r8d, 4
0x1800291cb  jnz     short loc_1800291DF
0x1800291cd  btr     ecx, 0Ah
0x1800291d1  mov     eax, ebx
0x1800291d3  and     eax, 400h
0x1800291d8  or      ecx, eax
0x1800291da  or      ecx, 4
0x1800291dd  mov     [rdi], ecx
0x1800291df  mov     eax, edx
0x1800291e1  lock cmpxchg [rsi], ecx
0x1800291e5  jnz     short loc_18002919E
0x1800291e7  test    r8d, r8d
0x1800291ea  jnz     short loc_1800291FC
0x1800291ec  mov     r8d, ebp
0x1800291ef  mov     edx, 3
0x1800291f4  mov     rcx, rsi
0x1800291f7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800291fc  mov     eax, [rdi]
0x1800291fe  test    al, 2
0x180029200  jnz     short loc_180029211
0x180029202  and     eax, 0FFFFF63Eh
0x180029207  and     ebx, 9C1h
0x18002920d  or      eax, ebx
0x18002920f  mov     [rdi], eax
0x180029211  mov     rbx, [rsp+38h+arg_10]
0x180029216  mov     rax, rdi
0x180029219  add     rsp, 20h
0x18002921d  pop     rdi
0x18002921e  pop     rsi
0x18002921f  pop     rbp
0x180029220  retn
```
