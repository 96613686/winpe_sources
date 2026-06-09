# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cdc4`
- end: `0x14000ce9d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e5f0`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000cdc4`
- `0x14000d768`

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
0x14000cdc4  mov     [rsp+arg_10], rbx
0x14000cdc9  mov     [rsp+arg_0], rcx
0x14000cdce  push    rbp
0x14000cdcf  push    rsi
0x14000cdd0  push    rdi
0x14000cdd1  sub     rsp, 20h
0x14000cdd5  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x14000cddc  mov     rdi, rdx
0x14000cddf  mov     qword ptr [rdx], 0
0x14000cde6  mov     eax, [rsi]
0x14000cde8  mov     [rdx], eax
0x14000cdea  and     eax, 6
0x14000cded  cmp     al, 6
0x14000cdef  jz      loc_14000CE8D
0x14000cdf5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cdfa  lea     r8, [rsp+38h+arg_0]
0x14000cdff  mov     dword ptr [rsp+38h+arg_0], 0
0x14000ce07  lea     rdx, [rsp+38h+arg_8]
0x14000ce0c  mov     ebp, eax
0x14000ce0e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x14000ce13  mov     eax, [rdi]
0x14000ce15  mov     rbx, [rsp+38h+arg_8]
0x14000ce1a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000ce1f  mov     edx, eax
0x14000ce21  mov     [rdi], eax
0x14000ce23  mov     ecx, eax
0x14000ce25  jz      short loc_14000CE40
0x14000ce27  test    dl, 2
0x14000ce2a  jnz     short loc_14000CE40
0x14000ce2c  and     ecx, 0FFFFF63Eh
0x14000ce32  mov     eax, ebx
0x14000ce34  and     eax, 9C1h
0x14000ce39  or      ecx, eax
0x14000ce3b  or      ecx, 2
0x14000ce3e  mov     [rdi], ecx
0x14000ce40  mov     r8d, edx
0x14000ce43  and     r8d, 4
0x14000ce47  jnz     short loc_14000CE5B
0x14000ce49  btr     ecx, 0Ah
0x14000ce4d  mov     eax, ebx
0x14000ce4f  and     eax, 400h
0x14000ce54  or      ecx, eax
0x14000ce56  or      ecx, 4
0x14000ce59  mov     [rdi], ecx
0x14000ce5b  mov     eax, edx
0x14000ce5d  lock cmpxchg [rsi], ecx
0x14000ce61  jnz     short loc_14000CE1A
0x14000ce63  test    r8d, r8d
0x14000ce66  jnz     short loc_14000CE78
0x14000ce68  mov     r8d, ebp
0x14000ce6b  mov     edx, 3
0x14000ce70  mov     rcx, rsi
0x14000ce73  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000ce78  mov     eax, [rdi]
0x14000ce7a  test    al, 2
0x14000ce7c  jnz     short loc_14000CE8D
0x14000ce7e  and     eax, 0FFFFF63Eh
0x14000ce83  and     ebx, 9C1h
0x14000ce89  or      eax, ebx
0x14000ce8b  mov     [rdi], eax
0x14000ce8d  mov     rbx, [rsp+38h+arg_10]
0x14000ce92  mov     rax, rdi
0x14000ce95  add     rsp, 20h
0x14000ce99  pop     rdi
0x14000ce9a  pop     rsi
0x14000ce9b  pop     rbp
0x14000ce9c  retn
```
