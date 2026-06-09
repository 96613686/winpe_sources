# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b124`
- end: `0x18000b29b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b384`

## callees

- `0x180004f18`
- `0x180008dc0`
- `0x18000b124`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
    }
    else
    {
      v6 = 0;
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b124  mov     [rsp+arg_8], rbx
0x18000b129  mov     [rsp+arg_10], rbp
0x18000b12e  mov     [rsp+arg_0], rcx
0x18000b133  push    rsi
0x18000b134  push    rdi
0x18000b135  push    r15
0x18000b137  sub     rsp, 20h
0x18000b13b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18000b142  mov     rbx, rdx
0x18000b145  mov     qword ptr [rdx], 0
0x18000b14c  mov     eax, [rsi]
0x18000b14e  mov     [rdx], eax
0x18000b150  and     eax, 6
0x18000b153  cmp     al, 6
0x18000b155  jz      loc_18000B285
0x18000b15b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b160  mov     ebp, eax
0x18000b162  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b16a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b171  test    rax, rax
0x18000b174  jz      short loc_18000B18E
0x18000b176  lea     r8, [rsp+38h+arg_0]
0x18000b17b  mov     edx, 3
0x18000b180  mov     ecx, 2F29A04h
0x18000b185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18a  mov     edx, eax
0x18000b18c  jmp     short loc_18000B19C
0x18000b18e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b195  test    rax, rax
0x18000b198  jnz     short loc_18000B176
0x18000b19a  xor     edx, edx
0x18000b19c  mov     r8d, edx
0x18000b19f  mov     eax, edx
0x18000b1a1  and     r8d, 0FFFFFF3Fh
0x18000b1a8  and     edx, 80h
0x18000b1ae  mov     ecx, r8d
0x18000b1b1  mov     r15d, 40h ; '@'
0x18000b1b7  and     ecx, 3
0x18000b1ba  and     eax, r15d
0x18000b1bd  shl     ecx, 2
0x18000b1c0  or      ecx, eax
0x18000b1c2  shl     ecx, 2
0x18000b1c5  or      ecx, edx
0x18000b1c7  lea     edi, ds:0[rcx*8]
0x18000b1ce  test    r8d, r8d
0x18000b1d1  jnz     short loc_18000B1D8
0x18000b1d3  mov     eax, r15d
0x18000b1d6  jmp     short loc_18000B1E2
0x18000b1d8  xor     eax, eax
0x18000b1da  cmp     r8d, 2
0x18000b1de  cmovz   eax, r15d
0x18000b1e2  or      edi, eax
0x18000b1e4  mov     eax, [rbx]
0x18000b1e6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b1eb  mov     edx, eax
0x18000b1ed  mov     [rbx], eax
0x18000b1ef  jz      short loc_18000B21F
0x18000b1f1  test    dl, 2
0x18000b1f4  jnz     short loc_18000B21F
0x18000b1f6  mov     eax, edi
0x18000b1f8  xor     eax, edx
0x18000b1fa  and     eax, 180h
0x18000b1ff  xor     eax, edx
0x18000b201  mov     ecx, eax
0x18000b203  xor     ecx, edi
0x18000b205  and     ecx, r15d
0x18000b208  xor     ecx, eax
0x18000b20a  or      ecx, 1
0x18000b20d  mov     eax, ecx
0x18000b20f  xor     eax, edi
0x18000b211  and     eax, 800h
0x18000b216  xor     eax, ecx
0x18000b218  or      eax, 2
0x18000b21b  mov     [rbx], eax
0x18000b21d  jmp     short loc_18000B221
0x18000b21f  mov     eax, edx
0x18000b221  mov     r8d, edx
0x18000b224  and     r8d, 4
0x18000b228  jnz     short loc_18000B23D
0x18000b22a  mov     ecx, edi
0x18000b22c  xor     ecx, eax
0x18000b22e  and     ecx, 400h
0x18000b234  xor     ecx, eax
0x18000b236  or      ecx, 4
0x18000b239  mov     [rbx], ecx
0x18000b23b  jmp     short loc_18000B23F
0x18000b23d  mov     ecx, eax
0x18000b23f  mov     eax, edx
0x18000b241  lock cmpxchg [rsi], ecx
0x18000b245  jnz     short loc_18000B1E6
0x18000b247  test    r8d, r8d
0x18000b24a  jnz     short loc_18000B25C
0x18000b24c  mov     r8d, ebp
0x18000b24f  mov     edx, 3
0x18000b254  mov     rcx, rsi
0x18000b257  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b25c  test    byte ptr [rbx], 2
0x18000b25f  jnz     short loc_18000B285
0x18000b261  mov     eax, [rbx]
0x18000b263  xor     eax, edi
0x18000b265  and     eax, 180h
0x18000b26a  xor     eax, [rbx]
0x18000b26c  mov     ecx, eax
0x18000b26e  xor     ecx, edi
0x18000b270  and     ecx, r15d
0x18000b273  xor     ecx, eax
0x18000b275  or      ecx, 1
0x18000b278  mov     eax, ecx
0x18000b27a  xor     eax, edi
0x18000b27c  and     eax, 800h
0x18000b281  xor     eax, ecx
0x18000b283  mov     [rbx], eax
0x18000b285  mov     rbp, [rsp+38h+arg_10]
0x18000b28a  mov     rax, rbx
0x18000b28d  mov     rbx, [rsp+38h+arg_8]
0x18000b292  add     rsp, 20h
0x18000b296  pop     r15
0x18000b298  pop     rdi
0x18000b299  pop     rsi
0x18000b29a  retn
```
