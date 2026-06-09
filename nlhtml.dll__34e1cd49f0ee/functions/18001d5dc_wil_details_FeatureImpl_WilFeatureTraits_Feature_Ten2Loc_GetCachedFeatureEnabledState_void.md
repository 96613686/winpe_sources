# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d5dc`
- end: `0x18001d6b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eba0`
- `0x18001ef50`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d5dc`
- `0x18001dec8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18001d5dc  mov     [rsp+arg_10], rbx
0x18001d5e1  mov     [rsp+arg_0], rcx
0x18001d5e6  push    rbp
0x18001d5e7  push    rsi
0x18001d5e8  push    rdi
0x18001d5e9  sub     rsp, 20h
0x18001d5ed  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18001d5f4  mov     rdi, rdx
0x18001d5f7  mov     qword ptr [rdx], 0
0x18001d5fe  mov     eax, [rsi]
0x18001d600  mov     [rdx], eax
0x18001d602  and     eax, 6
0x18001d605  cmp     al, 6
0x18001d607  jz      loc_18001D6A5
0x18001d60d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d612  lea     r8, [rsp+38h+arg_0]
0x18001d617  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d61f  lea     rdx, [rsp+38h+arg_8]
0x18001d624  mov     ebp, eax
0x18001d626  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18001d62b  mov     eax, [rdi]
0x18001d62d  mov     rbx, [rsp+38h+arg_8]
0x18001d632  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d637  mov     edx, eax
0x18001d639  mov     [rdi], eax
0x18001d63b  mov     ecx, eax
0x18001d63d  jz      short loc_18001D658
0x18001d63f  test    dl, 2
0x18001d642  jnz     short loc_18001D658
0x18001d644  and     ecx, 0FFFFF63Eh
0x18001d64a  mov     eax, ebx
0x18001d64c  and     eax, 9C1h
0x18001d651  or      ecx, eax
0x18001d653  or      ecx, 2
0x18001d656  mov     [rdi], ecx
0x18001d658  mov     r8d, edx
0x18001d65b  and     r8d, 4
0x18001d65f  jnz     short loc_18001D673
0x18001d661  btr     ecx, 0Ah
0x18001d665  mov     eax, ebx
0x18001d667  and     eax, 400h
0x18001d66c  or      ecx, eax
0x18001d66e  or      ecx, 4
0x18001d671  mov     [rdi], ecx
0x18001d673  mov     eax, edx
0x18001d675  lock cmpxchg [rsi], ecx
0x18001d679  jnz     short loc_18001D632
0x18001d67b  test    r8d, r8d
0x18001d67e  jnz     short loc_18001D690
0x18001d680  mov     r8d, ebp
0x18001d683  mov     edx, 3
0x18001d688  mov     rcx, rsi
0x18001d68b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d690  mov     eax, [rdi]
0x18001d692  test    al, 2
0x18001d694  jnz     short loc_18001D6A5
0x18001d696  and     eax, 0FFFFF63Eh
0x18001d69b  and     ebx, 9C1h
0x18001d6a1  or      eax, ebx
0x18001d6a3  mov     [rdi], eax
0x18001d6a5  mov     rbx, [rsp+38h+arg_10]
0x18001d6aa  mov     rax, rdi
0x18001d6ad  add     rsp, 20h
0x18001d6b1  pop     rdi
0x18001d6b2  pop     rsi
0x18001d6b3  pop     rbp
0x18001d6b4  retn
```
