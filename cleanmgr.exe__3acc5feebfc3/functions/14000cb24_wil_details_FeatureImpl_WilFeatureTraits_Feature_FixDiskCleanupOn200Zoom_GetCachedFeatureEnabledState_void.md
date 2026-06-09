# wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cb24`
- end: `0x14000cbfd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e45c`
- `0x14000ebe4`

## callees

- `0x140007508`
- `0x1400096d0`
- `0x14000cb24`
- `0x14000d5a4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_FixDiskCleanupOn200Zoom__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_FixDiskCleanupOn200Zoom__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_FixDiskCleanupOn200Zoom__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_FixDiskCleanupOn200Zoom__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000cb24  mov     [rsp+arg_10], rbx
0x14000cb29  mov     [rsp+arg_0], rcx
0x14000cb2e  push    rbp
0x14000cb2f  push    rsi
0x14000cb30  push    rdi
0x14000cb31  sub     rsp, 20h
0x14000cb35  mov     rsi, cs:Feature_FixDiskCleanupOn200Zoom__descriptor
0x14000cb3c  mov     rdi, rdx
0x14000cb3f  mov     qword ptr [rdx], 0
0x14000cb46  mov     eax, [rsi]
0x14000cb48  mov     [rdx], eax
0x14000cb4a  and     eax, 6
0x14000cb4d  cmp     al, 6
0x14000cb4f  jz      loc_14000CBED
0x14000cb55  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cb5a  lea     r8, [rsp+38h+arg_0]
0x14000cb5f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000cb67  lea     rdx, [rsp+38h+arg_8]
0x14000cb6c  mov     ebp, eax
0x14000cb6e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetCurrentFeatureEnabledState(int *)
0x14000cb73  mov     eax, [rdi]
0x14000cb75  mov     rbx, [rsp+38h+arg_8]
0x14000cb7a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000cb7f  mov     edx, eax
0x14000cb81  mov     [rdi], eax
0x14000cb83  mov     ecx, eax
0x14000cb85  jz      short loc_14000CBA0
0x14000cb87  test    dl, 2
0x14000cb8a  jnz     short loc_14000CBA0
0x14000cb8c  and     ecx, 0FFFFF63Eh
0x14000cb92  mov     eax, ebx
0x14000cb94  and     eax, 9C1h
0x14000cb99  or      ecx, eax
0x14000cb9b  or      ecx, 2
0x14000cb9e  mov     [rdi], ecx
0x14000cba0  mov     r8d, edx
0x14000cba3  and     r8d, 4
0x14000cba7  jnz     short loc_14000CBBB
0x14000cba9  btr     ecx, 0Ah
0x14000cbad  mov     eax, ebx
0x14000cbaf  and     eax, 400h
0x14000cbb4  or      ecx, eax
0x14000cbb6  or      ecx, 4
0x14000cbb9  mov     [rdi], ecx
0x14000cbbb  mov     eax, edx
0x14000cbbd  lock cmpxchg [rsi], ecx
0x14000cbc1  jnz     short loc_14000CB7A
0x14000cbc3  test    r8d, r8d
0x14000cbc6  jnz     short loc_14000CBD8
0x14000cbc8  mov     r8d, ebp
0x14000cbcb  mov     edx, 3
0x14000cbd0  mov     rcx, rsi
0x14000cbd3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000cbd8  mov     eax, [rdi]
0x14000cbda  test    al, 2
0x14000cbdc  jnz     short loc_14000CBED
0x14000cbde  and     eax, 0FFFFF63Eh
0x14000cbe3  and     ebx, 9C1h
0x14000cbe9  or      eax, ebx
0x14000cbeb  mov     [rdi], eax
0x14000cbed  mov     rbx, [rsp+38h+arg_10]
0x14000cbf2  mov     rax, rdi
0x14000cbf5  add     rsp, 20h
0x14000cbf9  pop     rdi
0x14000cbfa  pop     rsi
0x14000cbfb  pop     rbp
0x14000cbfc  retn
```
