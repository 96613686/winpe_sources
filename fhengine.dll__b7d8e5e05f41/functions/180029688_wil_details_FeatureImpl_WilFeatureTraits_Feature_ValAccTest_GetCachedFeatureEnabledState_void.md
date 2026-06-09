# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180029688`
- end: `0x180029761`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cb44`
- `0x18002e394`

## callees

- `0x180028ab4`
- `0x180029688`
- `0x180029ef8`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180029688  mov     [rsp+arg_10], rbx
0x18002968d  mov     [rsp+arg_0], rcx
0x180029692  push    rbp
0x180029693  push    rsi
0x180029694  push    rdi
0x180029695  sub     rsp, 20h
0x180029699  mov     rsi, cs:Feature_ValAccTest__descriptor
0x1800296a0  mov     rdi, rdx
0x1800296a3  mov     qword ptr [rdx], 0
0x1800296aa  mov     eax, [rsi]
0x1800296ac  mov     [rdx], eax
0x1800296ae  and     eax, 6
0x1800296b1  cmp     al, 6
0x1800296b3  jz      loc_180029751
0x1800296b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800296be  lea     r8, [rsp+38h+arg_0]
0x1800296c3  mov     dword ptr [rsp+38h+arg_0], 0
0x1800296cb  lea     rdx, [rsp+38h+arg_8]
0x1800296d0  mov     ebp, eax
0x1800296d2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x1800296d7  mov     eax, [rdi]
0x1800296d9  mov     rbx, [rsp+38h+arg_8]
0x1800296de  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800296e3  mov     edx, eax
0x1800296e5  mov     [rdi], eax
0x1800296e7  mov     ecx, eax
0x1800296e9  jz      short loc_180029704
0x1800296eb  test    dl, 2
0x1800296ee  jnz     short loc_180029704
0x1800296f0  and     ecx, 0FFFFF63Eh
0x1800296f6  mov     eax, ebx
0x1800296f8  and     eax, 9C1h
0x1800296fd  or      ecx, eax
0x1800296ff  or      ecx, 2
0x180029702  mov     [rdi], ecx
0x180029704  mov     r8d, edx
0x180029707  and     r8d, 4
0x18002970b  jnz     short loc_18002971F
0x18002970d  btr     ecx, 0Ah
0x180029711  mov     eax, ebx
0x180029713  and     eax, 400h
0x180029718  or      ecx, eax
0x18002971a  or      ecx, 4
0x18002971d  mov     [rdi], ecx
0x18002971f  mov     eax, edx
0x180029721  lock cmpxchg [rsi], ecx
0x180029725  jnz     short loc_1800296DE
0x180029727  test    r8d, r8d
0x18002972a  jnz     short loc_18002973C
0x18002972c  mov     r8d, ebp
0x18002972f  mov     edx, 3
0x180029734  mov     rcx, rsi
0x180029737  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002973c  mov     eax, [rdi]
0x18002973e  test    al, 2
0x180029740  jnz     short loc_180029751
0x180029742  and     eax, 0FFFFF63Eh
0x180029747  and     ebx, 9C1h
0x18002974d  or      eax, ebx
0x18002974f  mov     [rdi], eax
0x180029751  mov     rbx, [rsp+38h+arg_10]
0x180029756  mov     rax, rdi
0x180029759  add     rsp, 20h
0x18002975d  pop     rdi
0x18002975e  pop     rsi
0x18002975f  pop     rbp
0x180029760  retn
```
