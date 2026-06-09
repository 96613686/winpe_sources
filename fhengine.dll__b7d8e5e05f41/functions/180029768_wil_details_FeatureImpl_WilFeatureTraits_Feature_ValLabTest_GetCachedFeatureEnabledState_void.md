# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180029768`
- end: `0x180029841`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cbcc`

## callees

- `0x180028ab4`
- `0x180029768`
- `0x180029fd4`
- `0x18002d7b8`

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
0x180029768  mov     [rsp+arg_10], rbx
0x18002976d  mov     [rsp+arg_0], rcx
0x180029772  push    rbp
0x180029773  push    rsi
0x180029774  push    rdi
0x180029775  sub     rsp, 20h
0x180029779  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180029780  mov     rdi, rdx
0x180029783  mov     qword ptr [rdx], 0
0x18002978a  mov     eax, [rsi]
0x18002978c  mov     [rdx], eax
0x18002978e  and     eax, 6
0x180029791  cmp     al, 6
0x180029793  jz      loc_180029831
0x180029799  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002979e  lea     r8, [rsp+38h+arg_0]
0x1800297a3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800297ab  lea     rdx, [rsp+38h+arg_8]
0x1800297b0  mov     ebp, eax
0x1800297b2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x1800297b7  mov     eax, [rdi]
0x1800297b9  mov     rbx, [rsp+38h+arg_8]
0x1800297be  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800297c3  mov     edx, eax
0x1800297c5  mov     [rdi], eax
0x1800297c7  mov     ecx, eax
0x1800297c9  jz      short loc_1800297E4
0x1800297cb  test    dl, 2
0x1800297ce  jnz     short loc_1800297E4
0x1800297d0  and     ecx, 0FFFFF63Eh
0x1800297d6  mov     eax, ebx
0x1800297d8  and     eax, 9C1h
0x1800297dd  or      ecx, eax
0x1800297df  or      ecx, 2
0x1800297e2  mov     [rdi], ecx
0x1800297e4  mov     r8d, edx
0x1800297e7  and     r8d, 4
0x1800297eb  jnz     short loc_1800297FF
0x1800297ed  btr     ecx, 0Ah
0x1800297f1  mov     eax, ebx
0x1800297f3  and     eax, 400h
0x1800297f8  or      ecx, eax
0x1800297fa  or      ecx, 4
0x1800297fd  mov     [rdi], ecx
0x1800297ff  mov     eax, edx
0x180029801  lock cmpxchg [rsi], ecx
0x180029805  jnz     short loc_1800297BE
0x180029807  test    r8d, r8d
0x18002980a  jnz     short loc_18002981C
0x18002980c  mov     r8d, ebp
0x18002980f  mov     edx, 3
0x180029814  mov     rcx, rsi
0x180029817  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002981c  mov     eax, [rdi]
0x18002981e  test    al, 2
0x180029820  jnz     short loc_180029831
0x180029822  and     eax, 0FFFFF63Eh
0x180029827  and     ebx, 9C1h
0x18002982d  or      eax, ebx
0x18002982f  mov     [rdi], eax
0x180029831  mov     rbx, [rsp+38h+arg_10]
0x180029836  mov     rax, rdi
0x180029839  add     rsp, 20h
0x18002983d  pop     rdi
0x18002983e  pop     rsi
0x18002983f  pop     rbp
0x180029840  retn
```
