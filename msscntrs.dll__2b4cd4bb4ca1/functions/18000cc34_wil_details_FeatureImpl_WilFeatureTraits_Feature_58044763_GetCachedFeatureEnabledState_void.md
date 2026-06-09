# wil::details::FeatureImpl<__WilFeatureTraits_Feature_58044763>::GetCachedFeatureEnabledState(void)

- ea: `0x18000cc34`
- end: `0x18000cd0d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58044763@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800108fc`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000cc34`
- `0x18000d6a4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_58044763>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_58044763__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_58044763__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_58044763>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_58044763__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_58044763__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000cc34  mov     [rsp+arg_10], rbx
0x18000cc39  mov     [rsp+arg_0], rcx
0x18000cc3e  push    rbp
0x18000cc3f  push    rsi
0x18000cc40  push    rdi
0x18000cc41  sub     rsp, 20h
0x18000cc45  mov     rsi, cs:Feature_58044763__descriptor
0x18000cc4c  mov     rdi, rdx
0x18000cc4f  mov     qword ptr [rdx], 0
0x18000cc56  mov     eax, [rsi]
0x18000cc58  mov     [rdx], eax
0x18000cc5a  and     eax, 6
0x18000cc5d  cmp     al, 6
0x18000cc5f  jz      loc_18000CCFD
0x18000cc65  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000cc6a  lea     r8, [rsp+38h+arg_0]
0x18000cc6f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000cc77  lea     rdx, [rsp+38h+arg_8]
0x18000cc7c  mov     ebp, eax
0x18000cc7e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58044763@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58044763>::GetCurrentFeatureEnabledState(int *)
0x18000cc83  mov     eax, [rdi]
0x18000cc85  mov     rbx, [rsp+38h+arg_8]
0x18000cc8a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000cc8f  mov     edx, eax
0x18000cc91  mov     [rdi], eax
0x18000cc93  mov     ecx, eax
0x18000cc95  jz      short loc_18000CCB0
0x18000cc97  test    dl, 2
0x18000cc9a  jnz     short loc_18000CCB0
0x18000cc9c  and     ecx, 0FFFFF63Eh
0x18000cca2  mov     eax, ebx
0x18000cca4  and     eax, 9C1h
0x18000cca9  or      ecx, eax
0x18000ccab  or      ecx, 2
0x18000ccae  mov     [rdi], ecx
0x18000ccb0  mov     r8d, edx
0x18000ccb3  and     r8d, 4
0x18000ccb7  jnz     short loc_18000CCCB
0x18000ccb9  btr     ecx, 0Ah
0x18000ccbd  mov     eax, ebx
0x18000ccbf  and     eax, 400h
0x18000ccc4  or      ecx, eax
0x18000ccc6  or      ecx, 4
0x18000ccc9  mov     [rdi], ecx
0x18000cccb  mov     eax, edx
0x18000cccd  lock cmpxchg [rsi], ecx
0x18000ccd1  jnz     short loc_18000CC8A
0x18000ccd3  test    r8d, r8d
0x18000ccd6  jnz     short loc_18000CCE8
0x18000ccd8  mov     r8d, ebp
0x18000ccdb  mov     edx, 3
0x18000cce0  mov     rcx, rsi
0x18000cce3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000cce8  mov     eax, [rdi]
0x18000ccea  test    al, 2
0x18000ccec  jnz     short loc_18000CCFD
0x18000ccee  and     eax, 0FFFFF63Eh
0x18000ccf3  and     ebx, 9C1h
0x18000ccf9  or      eax, ebx
0x18000ccfb  mov     [rdi], eax
0x18000ccfd  mov     rbx, [rsp+38h+arg_10]
0x18000cd02  mov     rax, rdi
0x18000cd05  add     rsp, 20h
0x18000cd09  pop     rdi
0x18000cd0a  pop     rsi
0x18000cd0b  pop     rbp
0x18000cd0c  retn
```
