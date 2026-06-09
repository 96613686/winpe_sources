# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180008d54`
- end: `0x180008ec1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d5c`

## callees

- `0x1800084b4`
- `0x180008d54`
- `0x1800113c4`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v4);
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
0x180008d54  mov     [rsp+arg_8], rbx
0x180008d59  mov     [rsp+arg_10], rbp
0x180008d5e  mov     [rsp+arg_0], rcx
0x180008d63  push    rsi
0x180008d64  push    rdi
0x180008d65  push    r15
0x180008d67  sub     rsp, 20h
0x180008d6b  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180008d72  mov     rbx, rdx
0x180008d75  mov     qword ptr [rdx], 0
0x180008d7c  mov     eax, [rsi]
0x180008d7e  mov     [rdx], eax
0x180008d80  and     eax, 6
0x180008d83  cmp     al, 6
0x180008d85  jz      loc_180008EAB
0x180008d8b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008d90  mov     ebp, eax
0x180008d92  mov     dword ptr [rsp+38h+arg_0], 0
0x180008d9a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008da1  test    rax, rax
0x180008da4  jz      short loc_180008DBE
0x180008da6  lea     r8, [rsp+38h+arg_0]
0x180008dab  mov     edx, 3
0x180008db0  mov     ecx, 2AF34F8h
0x180008db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dba  mov     edx, eax
0x180008dbc  jmp     short loc_180008DCC
0x180008dbe  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008dc5  test    rax, rax
0x180008dc8  jnz     short loc_180008DA6
0x180008dca  xor     edx, edx
0x180008dcc  mov     r8d, edx
0x180008dcf  mov     eax, edx
0x180008dd1  and     r8d, 0FFFFFF3Fh
0x180008dd8  and     edx, 80h
0x180008dde  mov     ecx, r8d
0x180008de1  mov     r15d, 40h ; '@'
0x180008de7  and     ecx, 3
0x180008dea  and     eax, r15d
0x180008ded  shl     ecx, 2
0x180008df0  or      ecx, eax
0x180008df2  shl     ecx, 2
0x180008df5  or      ecx, edx
0x180008df7  lea     edi, ds:0[rcx*8]
0x180008dfe  test    r8d, r8d
0x180008e01  jnz     short loc_180008E08
0x180008e03  mov     eax, r15d
0x180008e06  jmp     short loc_180008E12
0x180008e08  xor     eax, eax
0x180008e0a  cmp     r8d, 2
0x180008e0e  cmovz   eax, r15d
0x180008e12  or      edi, eax
0x180008e14  mov     eax, [rbx]
0x180008e16  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008e1b  mov     edx, eax
0x180008e1d  mov     [rbx], eax
0x180008e1f  jz      short loc_180008E4B
0x180008e21  test    dl, 2
0x180008e24  jnz     short loc_180008E4B
0x180008e26  xor     eax, edi
0x180008e28  and     eax, 180h
0x180008e2d  xor     eax, edx
0x180008e2f  mov     ecx, eax
0x180008e31  xor     ecx, edi
0x180008e33  and     ecx, r15d
0x180008e36  xor     ecx, eax
0x180008e38  or      ecx, 1
0x180008e3b  mov     eax, ecx
0x180008e3d  xor     eax, edi
0x180008e3f  and     eax, 800h
0x180008e44  xor     eax, ecx
0x180008e46  or      eax, 2
0x180008e49  mov     [rbx], eax
0x180008e4b  mov     r8d, edx
0x180008e4e  mov     ecx, eax
0x180008e50  and     r8d, 4
0x180008e54  jnz     short loc_180008E65
0x180008e56  xor     ecx, edi
0x180008e58  and     ecx, 400h
0x180008e5e  xor     ecx, eax
0x180008e60  or      ecx, 4
0x180008e63  mov     [rbx], ecx
0x180008e65  mov     eax, edx
0x180008e67  lock cmpxchg [rsi], ecx
0x180008e6b  jnz     short loc_180008E16
0x180008e6d  test    r8d, r8d
0x180008e70  jnz     short loc_180008E82
0x180008e72  mov     r8d, ebp
0x180008e75  mov     edx, 3
0x180008e7a  mov     rcx, rsi
0x180008e7d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008e82  test    byte ptr [rbx], 2
0x180008e85  jnz     short loc_180008EAB
0x180008e87  mov     eax, [rbx]
0x180008e89  xor     eax, edi
0x180008e8b  and     eax, 180h
0x180008e90  xor     eax, [rbx]
0x180008e92  mov     ecx, eax
0x180008e94  xor     ecx, edi
0x180008e96  and     ecx, r15d
0x180008e99  xor     ecx, eax
0x180008e9b  or      ecx, 1
0x180008e9e  mov     eax, ecx
0x180008ea0  xor     eax, edi
0x180008ea2  and     eax, 800h
0x180008ea7  xor     eax, ecx
0x180008ea9  mov     [rbx], eax
0x180008eab  mov     rbp, [rsp+38h+arg_10]
0x180008eb0  mov     rax, rbx
0x180008eb3  mov     rbx, [rsp+38h+arg_8]
0x180008eb8  add     rsp, 20h
0x180008ebc  pop     r15
0x180008ebe  pop     rdi
0x180008ebf  pop     rsi
0x180008ec0  retn
```
