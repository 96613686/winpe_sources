# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e874`
- end: `0x18000e9e1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f9e8`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000e874`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
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
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
        3,
        v4);
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
0x18000e874  mov     [rsp+arg_8], rbx
0x18000e879  mov     [rsp+arg_10], rbp
0x18000e87e  mov     [rsp+arg_0], rcx
0x18000e883  push    rsi
0x18000e884  push    rdi
0x18000e885  push    r15
0x18000e887  sub     rsp, 20h
0x18000e88b  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000e892  mov     rbx, rdx
0x18000e895  mov     qword ptr [rdx], 0
0x18000e89c  mov     eax, [rsi]
0x18000e89e  mov     [rdx], eax
0x18000e8a0  and     eax, 6
0x18000e8a3  cmp     al, 6
0x18000e8a5  jz      loc_18000E9CB
0x18000e8ab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e8b0  mov     ebp, eax
0x18000e8b2  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e8ba  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e8c1  test    rax, rax
0x18000e8c4  jz      short loc_18000E8DE
0x18000e8c6  lea     r8, [rsp+38h+arg_0]
0x18000e8cb  mov     edx, 3
0x18000e8d0  mov     ecx, 2AF34F8h
0x18000e8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8da  mov     edx, eax
0x18000e8dc  jmp     short loc_18000E8EC
0x18000e8de  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e8e5  test    rax, rax
0x18000e8e8  jnz     short loc_18000E8C6
0x18000e8ea  xor     edx, edx
0x18000e8ec  mov     r8d, edx
0x18000e8ef  mov     eax, edx
0x18000e8f1  and     r8d, 0FFFFFF3Fh
0x18000e8f8  and     edx, 80h
0x18000e8fe  mov     ecx, r8d
0x18000e901  mov     r15d, 40h ; '@'
0x18000e907  and     ecx, 3
0x18000e90a  and     eax, r15d
0x18000e90d  shl     ecx, 2
0x18000e910  or      ecx, eax
0x18000e912  shl     ecx, 2
0x18000e915  or      ecx, edx
0x18000e917  lea     edi, ds:0[rcx*8]
0x18000e91e  test    r8d, r8d
0x18000e921  jnz     short loc_18000E928
0x18000e923  mov     eax, r15d
0x18000e926  jmp     short loc_18000E932
0x18000e928  xor     eax, eax
0x18000e92a  cmp     r8d, 2
0x18000e92e  cmovz   eax, r15d
0x18000e932  or      edi, eax
0x18000e934  mov     eax, [rbx]
0x18000e936  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e93b  mov     edx, eax
0x18000e93d  mov     [rbx], eax
0x18000e93f  jz      short loc_18000E96B
0x18000e941  test    dl, 2
0x18000e944  jnz     short loc_18000E96B
0x18000e946  xor     eax, edi
0x18000e948  and     eax, 180h
0x18000e94d  xor     eax, edx
0x18000e94f  mov     ecx, eax
0x18000e951  xor     ecx, edi
0x18000e953  and     ecx, r15d
0x18000e956  xor     ecx, eax
0x18000e958  or      ecx, 1
0x18000e95b  mov     eax, ecx
0x18000e95d  xor     eax, edi
0x18000e95f  and     eax, 800h
0x18000e964  xor     eax, ecx
0x18000e966  or      eax, 2
0x18000e969  mov     [rbx], eax
0x18000e96b  mov     r8d, edx
0x18000e96e  mov     ecx, eax
0x18000e970  and     r8d, 4
0x18000e974  jnz     short loc_18000E985
0x18000e976  xor     ecx, edi
0x18000e978  and     ecx, 400h
0x18000e97e  xor     ecx, eax
0x18000e980  or      ecx, 4
0x18000e983  mov     [rbx], ecx
0x18000e985  mov     eax, edx
0x18000e987  lock cmpxchg [rsi], ecx
0x18000e98b  jnz     short loc_18000E936
0x18000e98d  test    r8d, r8d
0x18000e990  jnz     short loc_18000E9A2
0x18000e992  mov     r8d, ebp
0x18000e995  mov     edx, 3
0x18000e99a  mov     rcx, rsi
0x18000e99d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e9a2  test    byte ptr [rbx], 2
0x18000e9a5  jnz     short loc_18000E9CB
0x18000e9a7  mov     eax, [rbx]
0x18000e9a9  xor     eax, edi
0x18000e9ab  and     eax, 180h
0x18000e9b0  xor     eax, [rbx]
0x18000e9b2  mov     ecx, eax
0x18000e9b4  xor     ecx, edi
0x18000e9b6  and     ecx, r15d
0x18000e9b9  xor     ecx, eax
0x18000e9bb  or      ecx, 1
0x18000e9be  mov     eax, ecx
0x18000e9c0  xor     eax, edi
0x18000e9c2  and     eax, 800h
0x18000e9c7  xor     eax, ecx
0x18000e9c9  mov     [rbx], eax
0x18000e9cb  mov     rbp, [rsp+38h+arg_10]
0x18000e9d0  mov     rax, rbx
0x18000e9d3  mov     rbx, [rsp+38h+arg_8]
0x18000e9d8  add     rsp, 20h
0x18000e9dc  pop     r15
0x18000e9de  pop     rdi
0x18000e9df  pop     rsi
0x18000e9e0  retn
```
