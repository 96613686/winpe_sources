# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d09c`
- end: `0x18001d175`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e880`
- `0x18001ef14`

## callees

- `0x180016c14`
- `0x180019b00`
- `0x18001d09c`
- `0x18001dbbc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFix_44936384__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_BugFix_44936384__descriptor,
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
0x18001d09c  mov     [rsp+arg_10], rbx
0x18001d0a1  mov     [rsp+arg_0], rcx
0x18001d0a6  push    rbp
0x18001d0a7  push    rsi
0x18001d0a8  push    rdi
0x18001d0a9  sub     rsp, 20h
0x18001d0ad  mov     rsi, cs:Feature_BugFix_44936384__descriptor
0x18001d0b4  mov     rdi, rdx
0x18001d0b7  mov     qword ptr [rdx], 0
0x18001d0be  mov     eax, [rsi]
0x18001d0c0  mov     [rdx], eax
0x18001d0c2  and     eax, 6
0x18001d0c5  cmp     al, 6
0x18001d0c7  jz      loc_18001D165
0x18001d0cd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d0d2  lea     r8, [rsp+38h+arg_0]
0x18001d0d7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001d0df  lea     rdx, [rsp+38h+arg_8]
0x18001d0e4  mov     ebp, eax
0x18001d0e6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCurrentFeatureEnabledState(int *)
0x18001d0eb  mov     eax, [rdi]
0x18001d0ed  mov     rbx, [rsp+38h+arg_8]
0x18001d0f2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001d0f7  mov     edx, eax
0x18001d0f9  mov     [rdi], eax
0x18001d0fb  mov     ecx, eax
0x18001d0fd  jz      short loc_18001D118
0x18001d0ff  test    dl, 2
0x18001d102  jnz     short loc_18001D118
0x18001d104  and     ecx, 0FFFFF63Eh
0x18001d10a  mov     eax, ebx
0x18001d10c  and     eax, 9C1h
0x18001d111  or      ecx, eax
0x18001d113  or      ecx, 2
0x18001d116  mov     [rdi], ecx
0x18001d118  mov     r8d, edx
0x18001d11b  and     r8d, 4
0x18001d11f  jnz     short loc_18001D133
0x18001d121  btr     ecx, 0Ah
0x18001d125  mov     eax, ebx
0x18001d127  and     eax, 400h
0x18001d12c  or      ecx, eax
0x18001d12e  or      ecx, 4
0x18001d131  mov     [rdi], ecx
0x18001d133  mov     eax, edx
0x18001d135  lock cmpxchg [rsi], ecx
0x18001d139  jnz     short loc_18001D0F2
0x18001d13b  test    r8d, r8d
0x18001d13e  jnz     short loc_18001D150
0x18001d140  mov     r8d, ebp
0x18001d143  mov     edx, 3
0x18001d148  mov     rcx, rsi
0x18001d14b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d150  mov     eax, [rdi]
0x18001d152  test    al, 2
0x18001d154  jnz     short loc_18001D165
0x18001d156  and     eax, 0FFFFF63Eh
0x18001d15b  and     ebx, 9C1h
0x18001d161  or      eax, ebx
0x18001d163  mov     [rdi], eax
0x18001d165  mov     rbx, [rsp+38h+arg_10]
0x18001d16a  mov     rax, rdi
0x18001d16d  add     rsp, 20h
0x18001d171  pop     rdi
0x18001d172  pop     rsi
0x18001d173  pop     rbp
0x18001d174  retn
```
