# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d2e4`
- end: `0x18000d45b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d7ec`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000d2e4`
- `0x180018010`

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
0x18000d2e4  mov     [rsp+arg_8], rbx
0x18000d2e9  mov     [rsp+arg_10], rbp
0x18000d2ee  mov     [rsp+arg_0], rcx
0x18000d2f3  push    rsi
0x18000d2f4  push    rdi
0x18000d2f5  push    r15
0x18000d2f7  sub     rsp, 20h
0x18000d2fb  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18000d302  mov     rbx, rdx
0x18000d305  mov     qword ptr [rdx], 0
0x18000d30c  mov     eax, [rsi]
0x18000d30e  mov     [rdx], eax
0x18000d310  and     eax, 6
0x18000d313  cmp     al, 6
0x18000d315  jz      loc_18000D445
0x18000d31b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d320  mov     ebp, eax
0x18000d322  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d32a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d331  test    rax, rax
0x18000d334  jz      short loc_18000D34E
0x18000d336  lea     r8, [rsp+38h+arg_0]
0x18000d33b  mov     edx, 3
0x18000d340  mov     ecx, 2F29A04h
0x18000d345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d34a  mov     edx, eax
0x18000d34c  jmp     short loc_18000D35C
0x18000d34e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d355  test    rax, rax
0x18000d358  jnz     short loc_18000D336
0x18000d35a  xor     edx, edx
0x18000d35c  mov     r8d, edx
0x18000d35f  mov     eax, edx
0x18000d361  and     r8d, 0FFFFFF3Fh
0x18000d368  and     edx, 80h
0x18000d36e  mov     ecx, r8d
0x18000d371  mov     r15d, 40h ; '@'
0x18000d377  and     ecx, 3
0x18000d37a  and     eax, r15d
0x18000d37d  shl     ecx, 2
0x18000d380  or      ecx, eax
0x18000d382  shl     ecx, 2
0x18000d385  or      ecx, edx
0x18000d387  lea     edi, ds:0[rcx*8]
0x18000d38e  test    r8d, r8d
0x18000d391  jnz     short loc_18000D398
0x18000d393  mov     eax, r15d
0x18000d396  jmp     short loc_18000D3A2
0x18000d398  xor     eax, eax
0x18000d39a  cmp     r8d, 2
0x18000d39e  cmovz   eax, r15d
0x18000d3a2  or      edi, eax
0x18000d3a4  mov     eax, [rbx]
0x18000d3a6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d3ab  mov     edx, eax
0x18000d3ad  mov     [rbx], eax
0x18000d3af  jz      short loc_18000D3DF
0x18000d3b1  test    dl, 2
0x18000d3b4  jnz     short loc_18000D3DF
0x18000d3b6  mov     eax, edi
0x18000d3b8  xor     eax, edx
0x18000d3ba  and     eax, 180h
0x18000d3bf  xor     eax, edx
0x18000d3c1  mov     ecx, eax
0x18000d3c3  xor     ecx, edi
0x18000d3c5  and     ecx, r15d
0x18000d3c8  xor     ecx, eax
0x18000d3ca  or      ecx, 1
0x18000d3cd  mov     eax, ecx
0x18000d3cf  xor     eax, edi
0x18000d3d1  and     eax, 800h
0x18000d3d6  xor     eax, ecx
0x18000d3d8  or      eax, 2
0x18000d3db  mov     [rbx], eax
0x18000d3dd  jmp     short loc_18000D3E1
0x18000d3df  mov     eax, edx
0x18000d3e1  mov     r8d, edx
0x18000d3e4  and     r8d, 4
0x18000d3e8  jnz     short loc_18000D3FD
0x18000d3ea  mov     ecx, edi
0x18000d3ec  xor     ecx, eax
0x18000d3ee  and     ecx, 400h
0x18000d3f4  xor     ecx, eax
0x18000d3f6  or      ecx, 4
0x18000d3f9  mov     [rbx], ecx
0x18000d3fb  jmp     short loc_18000D3FF
0x18000d3fd  mov     ecx, eax
0x18000d3ff  mov     eax, edx
0x18000d401  lock cmpxchg [rsi], ecx
0x18000d405  jnz     short loc_18000D3A6
0x18000d407  test    r8d, r8d
0x18000d40a  jnz     short loc_18000D41C
0x18000d40c  mov     r8d, ebp
0x18000d40f  mov     edx, 3
0x18000d414  mov     rcx, rsi
0x18000d417  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d41c  test    byte ptr [rbx], 2
0x18000d41f  jnz     short loc_18000D445
0x18000d421  mov     eax, [rbx]
0x18000d423  xor     eax, edi
0x18000d425  and     eax, 180h
0x18000d42a  xor     eax, [rbx]
0x18000d42c  mov     ecx, eax
0x18000d42e  xor     ecx, edi
0x18000d430  and     ecx, r15d
0x18000d433  xor     ecx, eax
0x18000d435  or      ecx, 1
0x18000d438  mov     eax, ecx
0x18000d43a  xor     eax, edi
0x18000d43c  and     eax, 800h
0x18000d441  xor     eax, ecx
0x18000d443  mov     [rbx], eax
0x18000d445  mov     rbp, [rsp+38h+arg_10]
0x18000d44a  mov     rax, rbx
0x18000d44d  mov     rbx, [rsp+38h+arg_8]
0x18000d452  add     rsp, 20h
0x18000d456  pop     r15
0x18000d458  pop     rdi
0x18000d459  pop     rsi
0x18000d45a  retn
```
