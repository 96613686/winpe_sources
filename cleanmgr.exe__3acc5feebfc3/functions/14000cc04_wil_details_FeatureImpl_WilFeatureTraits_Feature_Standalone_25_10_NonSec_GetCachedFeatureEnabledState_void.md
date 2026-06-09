# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cc04`
- end: `0x14000ccdd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e4e8`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000cc04`
- `0x14000d670`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000cc04  mov     [rsp+arg_10], rbx
0x14000cc09  mov     [rsp+arg_0], rcx
0x14000cc0e  push    rbp
0x14000cc0f  push    rsi
0x14000cc10  push    rdi
0x14000cc11  sub     rsp, 20h
0x14000cc15  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x14000cc1c  mov     rdi, rdx
0x14000cc1f  mov     qword ptr [rdx], 0
0x14000cc26  mov     eax, [rsi]
0x14000cc28  mov     [rdx], eax
0x14000cc2a  and     eax, 6
0x14000cc2d  cmp     al, 6
0x14000cc2f  jz      loc_14000CCCD
0x14000cc35  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cc3a  lea     r8, [rsp+38h+arg_0]
0x14000cc3f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000cc47  lea     rdx, [rsp+38h+arg_8]
0x14000cc4c  mov     ebp, eax
0x14000cc4e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x14000cc53  mov     eax, [rdi]
0x14000cc55  mov     rbx, [rsp+38h+arg_8]
0x14000cc5a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000cc5f  mov     edx, eax
0x14000cc61  mov     [rdi], eax
0x14000cc63  mov     ecx, eax
0x14000cc65  jz      short loc_14000CC80
0x14000cc67  test    dl, 2
0x14000cc6a  jnz     short loc_14000CC80
0x14000cc6c  and     ecx, 0FFFFF63Eh
0x14000cc72  mov     eax, ebx
0x14000cc74  and     eax, 9C1h
0x14000cc79  or      ecx, eax
0x14000cc7b  or      ecx, 2
0x14000cc7e  mov     [rdi], ecx
0x14000cc80  mov     r8d, edx
0x14000cc83  and     r8d, 4
0x14000cc87  jnz     short loc_14000CC9B
0x14000cc89  btr     ecx, 0Ah
0x14000cc8d  mov     eax, ebx
0x14000cc8f  and     eax, 400h
0x14000cc94  or      ecx, eax
0x14000cc96  or      ecx, 4
0x14000cc99  mov     [rdi], ecx
0x14000cc9b  mov     eax, edx
0x14000cc9d  lock cmpxchg [rsi], ecx
0x14000cca1  jnz     short loc_14000CC5A
0x14000cca3  test    r8d, r8d
0x14000cca6  jnz     short loc_14000CCB8
0x14000cca8  mov     r8d, ebp
0x14000ccab  mov     edx, 3
0x14000ccb0  mov     rcx, rsi
0x14000ccb3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000ccb8  mov     eax, [rdi]
0x14000ccba  test    al, 2
0x14000ccbc  jnz     short loc_14000CCCD
0x14000ccbe  and     eax, 0FFFFF63Eh
0x14000ccc3  and     ebx, 9C1h
0x14000ccc9  or      eax, ebx
0x14000cccb  mov     [rdi], eax
0x14000cccd  mov     rbx, [rsp+38h+arg_10]
0x14000ccd2  mov     rax, rdi
0x14000ccd5  add     rsp, 20h
0x14000ccd9  pop     rdi
0x14000ccda  pop     rsi
0x14000ccdb  pop     rbp
0x14000ccdc  retn
```
