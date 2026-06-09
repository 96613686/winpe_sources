# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cea4`
- end: `0x14000cf7d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e674`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000cea4`
- `0x14000d7e4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000cea4  mov     [rsp+arg_10], rbx
0x14000cea9  mov     [rsp+arg_0], rcx
0x14000ceae  push    rbp
0x14000ceaf  push    rsi
0x14000ceb0  push    rdi
0x14000ceb1  sub     rsp, 20h
0x14000ceb5  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x14000cebc  mov     rdi, rdx
0x14000cebf  mov     qword ptr [rdx], 0
0x14000cec6  mov     eax, [rsi]
0x14000cec8  mov     [rdx], eax
0x14000ceca  and     eax, 6
0x14000cecd  cmp     al, 6
0x14000cecf  jz      loc_14000CF6D
0x14000ced5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000ceda  lea     r8, [rsp+38h+arg_0]
0x14000cedf  mov     dword ptr [rsp+38h+arg_0], 0
0x14000cee7  lea     rdx, [rsp+38h+arg_8]
0x14000ceec  mov     ebp, eax
0x14000ceee  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x14000cef3  mov     eax, [rdi]
0x14000cef5  mov     rbx, [rsp+38h+arg_8]
0x14000cefa  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000ceff  mov     edx, eax
0x14000cf01  mov     [rdi], eax
0x14000cf03  mov     ecx, eax
0x14000cf05  jz      short loc_14000CF20
0x14000cf07  test    dl, 2
0x14000cf0a  jnz     short loc_14000CF20
0x14000cf0c  and     ecx, 0FFFFF63Eh
0x14000cf12  mov     eax, ebx
0x14000cf14  and     eax, 9C1h
0x14000cf19  or      ecx, eax
0x14000cf1b  or      ecx, 2
0x14000cf1e  mov     [rdi], ecx
0x14000cf20  mov     r8d, edx
0x14000cf23  and     r8d, 4
0x14000cf27  jnz     short loc_14000CF3B
0x14000cf29  btr     ecx, 0Ah
0x14000cf2d  mov     eax, ebx
0x14000cf2f  and     eax, 400h
0x14000cf34  or      ecx, eax
0x14000cf36  or      ecx, 4
0x14000cf39  mov     [rdi], ecx
0x14000cf3b  mov     eax, edx
0x14000cf3d  lock cmpxchg [rsi], ecx
0x14000cf41  jnz     short loc_14000CEFA
0x14000cf43  test    r8d, r8d
0x14000cf46  jnz     short loc_14000CF58
0x14000cf48  mov     r8d, ebp
0x14000cf4b  mov     edx, 3
0x14000cf50  mov     rcx, rsi
0x14000cf53  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000cf58  mov     eax, [rdi]
0x14000cf5a  test    al, 2
0x14000cf5c  jnz     short loc_14000CF6D
0x14000cf5e  and     eax, 0FFFFF63Eh
0x14000cf63  and     ebx, 9C1h
0x14000cf69  or      eax, ebx
0x14000cf6b  mov     [rdi], eax
0x14000cf6d  mov     rbx, [rsp+38h+arg_10]
0x14000cf72  mov     rax, rdi
0x14000cf75  add     rsp, 20h
0x14000cf79  pop     rdi
0x14000cf7a  pop     rsi
0x14000cf7b  pop     rbp
0x14000cf7c  retn
```
