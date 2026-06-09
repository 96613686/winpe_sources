# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800294c8`
- end: `0x1800295a1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ca34`
- `0x18002e31c`

## callees

- `0x180028ab4`
- `0x1800294c8`
- `0x180029d20`
- `0x18002d7b8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestAccPerf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800294c8  mov     [rsp+arg_10], rbx
0x1800294cd  mov     [rsp+arg_0], rcx
0x1800294d2  push    rbp
0x1800294d3  push    rsi
0x1800294d4  push    rdi
0x1800294d5  sub     rsp, 20h
0x1800294d9  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x1800294e0  mov     rdi, rdx
0x1800294e3  mov     qword ptr [rdx], 0
0x1800294ea  mov     eax, [rsi]
0x1800294ec  mov     [rdx], eax
0x1800294ee  and     eax, 6
0x1800294f1  cmp     al, 6
0x1800294f3  jz      loc_180029591
0x1800294f9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800294fe  lea     r8, [rsp+38h+arg_0]
0x180029503  mov     dword ptr [rsp+38h+arg_0], 0
0x18002950b  lea     rdx, [rsp+38h+arg_8]
0x180029510  mov     ebp, eax
0x180029512  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180029517  mov     eax, [rdi]
0x180029519  mov     rbx, [rsp+38h+arg_8]
0x18002951e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180029523  mov     edx, eax
0x180029525  mov     [rdi], eax
0x180029527  mov     ecx, eax
0x180029529  jz      short loc_180029544
0x18002952b  test    dl, 2
0x18002952e  jnz     short loc_180029544
0x180029530  and     ecx, 0FFFFF63Eh
0x180029536  mov     eax, ebx
0x180029538  and     eax, 9C1h
0x18002953d  or      ecx, eax
0x18002953f  or      ecx, 2
0x180029542  mov     [rdi], ecx
0x180029544  mov     r8d, edx
0x180029547  and     r8d, 4
0x18002954b  jnz     short loc_18002955F
0x18002954d  btr     ecx, 0Ah
0x180029551  mov     eax, ebx
0x180029553  and     eax, 400h
0x180029558  or      ecx, eax
0x18002955a  or      ecx, 4
0x18002955d  mov     [rdi], ecx
0x18002955f  mov     eax, edx
0x180029561  lock cmpxchg [rsi], ecx
0x180029565  jnz     short loc_18002951E
0x180029567  test    r8d, r8d
0x18002956a  jnz     short loc_18002957C
0x18002956c  mov     r8d, ebp
0x18002956f  mov     edx, 3
0x180029574  mov     rcx, rsi
0x180029577  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002957c  mov     eax, [rdi]
0x18002957e  test    al, 2
0x180029580  jnz     short loc_180029591
0x180029582  and     eax, 0FFFFF63Eh
0x180029587  and     ebx, 9C1h
0x18002958d  or      eax, ebx
0x18002958f  mov     [rdi], eax
0x180029591  mov     rbx, [rsp+38h+arg_10]
0x180029596  mov     rax, rdi
0x180029599  add     rsp, 20h
0x18002959d  pop     rdi
0x18002959e  pop     rsi
0x18002959f  pop     rbp
0x1800295a0  retn
```
