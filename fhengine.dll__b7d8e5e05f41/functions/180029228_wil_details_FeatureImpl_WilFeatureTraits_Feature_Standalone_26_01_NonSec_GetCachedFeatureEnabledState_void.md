# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180029228`
- end: `0x180029301`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c8a4`

## callees

- `0x180028ab4`
- `0x180029228`
- `0x180029b3c`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180029228  mov     [rsp+arg_10], rbx
0x18002922d  mov     [rsp+arg_0], rcx
0x180029232  push    rbp
0x180029233  push    rsi
0x180029234  push    rdi
0x180029235  sub     rsp, 20h
0x180029239  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180029240  mov     rdi, rdx
0x180029243  mov     qword ptr [rdx], 0
0x18002924a  mov     eax, [rsi]
0x18002924c  mov     [rdx], eax
0x18002924e  and     eax, 6
0x180029251  cmp     al, 6
0x180029253  jz      loc_1800292F1
0x180029259  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002925e  lea     r8, [rsp+38h+arg_0]
0x180029263  mov     dword ptr [rsp+38h+arg_0], 0
0x18002926b  lea     rdx, [rsp+38h+arg_8]
0x180029270  mov     ebp, eax
0x180029272  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180029277  mov     eax, [rdi]
0x180029279  mov     rbx, [rsp+38h+arg_8]
0x18002927e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180029283  mov     edx, eax
0x180029285  mov     [rdi], eax
0x180029287  mov     ecx, eax
0x180029289  jz      short loc_1800292A4
0x18002928b  test    dl, 2
0x18002928e  jnz     short loc_1800292A4
0x180029290  and     ecx, 0FFFFF63Eh
0x180029296  mov     eax, ebx
0x180029298  and     eax, 9C1h
0x18002929d  or      ecx, eax
0x18002929f  or      ecx, 2
0x1800292a2  mov     [rdi], ecx
0x1800292a4  mov     r8d, edx
0x1800292a7  and     r8d, 4
0x1800292ab  jnz     short loc_1800292BF
0x1800292ad  btr     ecx, 0Ah
0x1800292b1  mov     eax, ebx
0x1800292b3  and     eax, 400h
0x1800292b8  or      ecx, eax
0x1800292ba  or      ecx, 4
0x1800292bd  mov     [rdi], ecx
0x1800292bf  mov     eax, edx
0x1800292c1  lock cmpxchg [rsi], ecx
0x1800292c5  jnz     short loc_18002927E
0x1800292c7  test    r8d, r8d
0x1800292ca  jnz     short loc_1800292DC
0x1800292cc  mov     r8d, ebp
0x1800292cf  mov     edx, 3
0x1800292d4  mov     rcx, rsi
0x1800292d7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800292dc  mov     eax, [rdi]
0x1800292de  test    al, 2
0x1800292e0  jnz     short loc_1800292F1
0x1800292e2  and     eax, 0FFFFF63Eh
0x1800292e7  and     ebx, 9C1h
0x1800292ed  or      eax, ebx
0x1800292ef  mov     [rdi], eax
0x1800292f1  mov     rbx, [rsp+38h+arg_10]
0x1800292f6  mov     rax, rdi
0x1800292f9  add     rsp, 20h
0x1800292fd  pop     rdi
0x1800292fe  pop     rsi
0x1800292ff  pop     rbp
0x180029300  retn
```
