# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b7d0`
- end: `0x18001b947`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bd78`

## callees

- `0x180009e0c`
- `0x18000bbb0`
- `0x18001b7d0`
- `0x180033010`

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
0x18001b7d0  mov     [rsp+arg_8], rbx
0x18001b7d5  mov     [rsp+arg_10], rbp
0x18001b7da  mov     [rsp+arg_0], rcx
0x18001b7df  push    rsi
0x18001b7e0  push    rdi
0x18001b7e1  push    r15
0x18001b7e3  sub     rsp, 20h
0x18001b7e7  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18001b7ee  mov     rbx, rdx
0x18001b7f1  mov     qword ptr [rdx], 0
0x18001b7f8  mov     eax, [rsi]
0x18001b7fa  mov     [rdx], eax
0x18001b7fc  and     eax, 6
0x18001b7ff  cmp     al, 6
0x18001b801  jz      loc_18001B931
0x18001b807  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b80c  mov     ebp, eax
0x18001b80e  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b816  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001b81d  test    rax, rax
0x18001b820  jz      short loc_18001B83A
0x18001b822  lea     r8, [rsp+38h+arg_0]
0x18001b827  mov     edx, 3
0x18001b82c  mov     ecx, 2F29A04h
0x18001b831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b836  mov     edx, eax
0x18001b838  jmp     short loc_18001B848
0x18001b83a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001b841  test    rax, rax
0x18001b844  jnz     short loc_18001B822
0x18001b846  xor     edx, edx
0x18001b848  mov     r8d, edx
0x18001b84b  mov     eax, edx
0x18001b84d  and     r8d, 0FFFFFF3Fh
0x18001b854  and     edx, 80h
0x18001b85a  mov     ecx, r8d
0x18001b85d  mov     r15d, 40h ; '@'
0x18001b863  and     ecx, 3
0x18001b866  and     eax, r15d
0x18001b869  shl     ecx, 2
0x18001b86c  or      ecx, eax
0x18001b86e  shl     ecx, 2
0x18001b871  or      ecx, edx
0x18001b873  lea     edi, ds:0[rcx*8]
0x18001b87a  test    r8d, r8d
0x18001b87d  jnz     short loc_18001B884
0x18001b87f  mov     eax, r15d
0x18001b882  jmp     short loc_18001B88E
0x18001b884  xor     eax, eax
0x18001b886  cmp     r8d, 2
0x18001b88a  cmovz   eax, r15d
0x18001b88e  or      edi, eax
0x18001b890  mov     eax, [rbx]
0x18001b892  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b897  mov     edx, eax
0x18001b899  mov     [rbx], eax
0x18001b89b  jz      short loc_18001B8CB
0x18001b89d  test    dl, 2
0x18001b8a0  jnz     short loc_18001B8CB
0x18001b8a2  mov     eax, edi
0x18001b8a4  xor     eax, edx
0x18001b8a6  and     eax, 180h
0x18001b8ab  xor     eax, edx
0x18001b8ad  mov     ecx, eax
0x18001b8af  xor     ecx, edi
0x18001b8b1  and     ecx, r15d
0x18001b8b4  xor     ecx, eax
0x18001b8b6  or      ecx, 1
0x18001b8b9  mov     eax, ecx
0x18001b8bb  xor     eax, edi
0x18001b8bd  and     eax, 800h
0x18001b8c2  xor     eax, ecx
0x18001b8c4  or      eax, 2
0x18001b8c7  mov     [rbx], eax
0x18001b8c9  jmp     short loc_18001B8CD
0x18001b8cb  mov     eax, edx
0x18001b8cd  mov     r8d, edx
0x18001b8d0  and     r8d, 4
0x18001b8d4  jnz     short loc_18001B8E9
0x18001b8d6  mov     ecx, edi
0x18001b8d8  xor     ecx, eax
0x18001b8da  and     ecx, 400h
0x18001b8e0  xor     ecx, eax
0x18001b8e2  or      ecx, 4
0x18001b8e5  mov     [rbx], ecx
0x18001b8e7  jmp     short loc_18001B8EB
0x18001b8e9  mov     ecx, eax
0x18001b8eb  mov     eax, edx
0x18001b8ed  lock cmpxchg [rsi], ecx
0x18001b8f1  jnz     short loc_18001B892
0x18001b8f3  test    r8d, r8d
0x18001b8f6  jnz     short loc_18001B908
0x18001b8f8  mov     r8d, ebp
0x18001b8fb  mov     edx, 3
0x18001b900  mov     rcx, rsi
0x18001b903  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b908  test    byte ptr [rbx], 2
0x18001b90b  jnz     short loc_18001B931
0x18001b90d  mov     eax, [rbx]
0x18001b90f  xor     eax, edi
0x18001b911  and     eax, 180h
0x18001b916  xor     eax, [rbx]
0x18001b918  mov     ecx, eax
0x18001b91a  xor     ecx, edi
0x18001b91c  and     ecx, r15d
0x18001b91f  xor     ecx, eax
0x18001b921  or      ecx, 1
0x18001b924  mov     eax, ecx
0x18001b926  xor     eax, edi
0x18001b928  and     eax, 800h
0x18001b92d  xor     eax, ecx
0x18001b92f  mov     [rbx], eax
0x18001b931  mov     rbp, [rsp+38h+arg_10]
0x18001b936  mov     rax, rbx
0x18001b939  mov     rbx, [rsp+38h+arg_8]
0x18001b93e  add     rsp, 20h
0x18001b942  pop     r15
0x18001b944  pop     rdi
0x18001b945  pop     rsi
0x18001b946  retn
```
