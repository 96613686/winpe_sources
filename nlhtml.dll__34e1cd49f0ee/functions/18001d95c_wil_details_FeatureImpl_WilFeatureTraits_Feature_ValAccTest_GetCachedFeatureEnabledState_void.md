# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d95c`
- end: `0x18001da35`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001edc0`
- `0x18001f040`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d95c`
- `0x18001e258`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001d95c  mov     [rsp+arg_10], rbx
0x18001d961  mov     [rsp+arg_0], rcx
0x18001d966  push    rbp
0x18001d967  push    rsi
0x18001d968  push    rdi
0x18001d969  sub     rsp, 20h
0x18001d96d  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18001d974  mov     rdi, rdx
0x18001d977  mov     qword ptr [rdx], 0
0x18001d97e  mov     eax, [rsi]
0x18001d980  mov     [rdx], eax
0x18001d982  and     eax, 6
0x18001d985  cmp     al, 6
0x18001d987  jz      loc_18001DA25
0x18001d98d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d992  lea     r8, [rsp+38h+arg_0]
0x18001d997  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d99f  lea     rdx, [rsp+38h+arg_8]
0x18001d9a4  mov     ebp, eax
0x18001d9a6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18001d9ab  mov     eax, [rdi]
0x18001d9ad  mov     rbx, [rsp+38h+arg_8]
0x18001d9b2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d9b7  mov     edx, eax
0x18001d9b9  mov     [rdi], eax
0x18001d9bb  mov     ecx, eax
0x18001d9bd  jz      short loc_18001D9D8
0x18001d9bf  test    dl, 2
0x18001d9c2  jnz     short loc_18001D9D8
0x18001d9c4  and     ecx, 0FFFFF63Eh
0x18001d9ca  mov     eax, ebx
0x18001d9cc  and     eax, 9C1h
0x18001d9d1  or      ecx, eax
0x18001d9d3  or      ecx, 2
0x18001d9d6  mov     [rdi], ecx
0x18001d9d8  mov     r8d, edx
0x18001d9db  and     r8d, 4
0x18001d9df  jnz     short loc_18001D9F3
0x18001d9e1  btr     ecx, 0Ah
0x18001d9e5  mov     eax, ebx
0x18001d9e7  and     eax, 400h
0x18001d9ec  or      ecx, eax
0x18001d9ee  or      ecx, 4
0x18001d9f1  mov     [rdi], ecx
0x18001d9f3  mov     eax, edx
0x18001d9f5  lock cmpxchg [rsi], ecx
0x18001d9f9  jnz     short loc_18001D9B2
0x18001d9fb  test    r8d, r8d
0x18001d9fe  jnz     short loc_18001DA10
0x18001da00  mov     r8d, ebp
0x18001da03  mov     edx, 3
0x18001da08  mov     rcx, rsi
0x18001da0b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001da10  mov     eax, [rdi]
0x18001da12  test    al, 2
0x18001da14  jnz     short loc_18001DA25
0x18001da16  and     eax, 0FFFFF63Eh
0x18001da1b  and     ebx, 9C1h
0x18001da21  or      eax, ebx
0x18001da23  mov     [rdi], eax
0x18001da25  mov     rbx, [rsp+38h+arg_10]
0x18001da2a  mov     rax, rdi
0x18001da2d  add     rsp, 20h
0x18001da31  pop     rdi
0x18001da32  pop     rsi
0x18001da33  pop     rbp
0x18001da34  retn
```
