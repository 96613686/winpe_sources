# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000cffc`
- end: `0x18000d169`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800130b0`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000cffc`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v4);
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
0x18000cffc  mov     [rsp+arg_8], rbx
0x18000d001  mov     [rsp+arg_10], rbp
0x18000d006  mov     [rsp+arg_0], rcx
0x18000d00b  push    rsi
0x18000d00c  push    rdi
0x18000d00d  push    r15
0x18000d00f  sub     rsp, 20h
0x18000d013  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000d01a  mov     rbx, rdx
0x18000d01d  mov     qword ptr [rdx], 0
0x18000d024  mov     eax, [rsi]
0x18000d026  mov     [rdx], eax
0x18000d028  and     eax, 6
0x18000d02b  cmp     al, 6
0x18000d02d  jz      loc_18000D153
0x18000d033  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d038  mov     ebp, eax
0x18000d03a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d042  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d049  test    rax, rax
0x18000d04c  jz      short loc_18000D066
0x18000d04e  lea     r8, [rsp+38h+arg_0]
0x18000d053  mov     edx, 3
0x18000d058  mov     ecx, 37E286Ch
0x18000d05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d062  mov     edx, eax
0x18000d064  jmp     short loc_18000D074
0x18000d066  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d06d  test    rax, rax
0x18000d070  jnz     short loc_18000D04E
0x18000d072  xor     edx, edx
0x18000d074  mov     r8d, edx
0x18000d077  mov     eax, edx
0x18000d079  and     r8d, 0FFFFFF3Fh
0x18000d080  and     edx, 80h
0x18000d086  mov     ecx, r8d
0x18000d089  mov     r15d, 40h ; '@'
0x18000d08f  and     ecx, 3
0x18000d092  and     eax, r15d
0x18000d095  shl     ecx, 2
0x18000d098  or      ecx, eax
0x18000d09a  shl     ecx, 2
0x18000d09d  or      ecx, edx
0x18000d09f  lea     edi, ds:0[rcx*8]
0x18000d0a6  test    r8d, r8d
0x18000d0a9  jnz     short loc_18000D0B0
0x18000d0ab  mov     eax, r15d
0x18000d0ae  jmp     short loc_18000D0BA
0x18000d0b0  xor     eax, eax
0x18000d0b2  cmp     r8d, 2
0x18000d0b6  cmovz   eax, r15d
0x18000d0ba  or      edi, eax
0x18000d0bc  mov     eax, [rbx]
0x18000d0be  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d0c3  mov     edx, eax
0x18000d0c5  mov     [rbx], eax
0x18000d0c7  jz      short loc_18000D0F3
0x18000d0c9  test    dl, 2
0x18000d0cc  jnz     short loc_18000D0F3
0x18000d0ce  xor     eax, edi
0x18000d0d0  and     eax, 180h
0x18000d0d5  xor     eax, edx
0x18000d0d7  mov     ecx, eax
0x18000d0d9  xor     ecx, edi
0x18000d0db  and     ecx, r15d
0x18000d0de  xor     ecx, eax
0x18000d0e0  or      ecx, 1
0x18000d0e3  mov     eax, ecx
0x18000d0e5  xor     eax, edi
0x18000d0e7  and     eax, 800h
0x18000d0ec  xor     eax, ecx
0x18000d0ee  or      eax, 2
0x18000d0f1  mov     [rbx], eax
0x18000d0f3  mov     r8d, edx
0x18000d0f6  mov     ecx, eax
0x18000d0f8  and     r8d, 4
0x18000d0fc  jnz     short loc_18000D10D
0x18000d0fe  xor     ecx, edi
0x18000d100  and     ecx, 400h
0x18000d106  xor     ecx, eax
0x18000d108  or      ecx, 4
0x18000d10b  mov     [rbx], ecx
0x18000d10d  mov     eax, edx
0x18000d10f  lock cmpxchg [rsi], ecx
0x18000d113  jnz     short loc_18000D0BE
0x18000d115  test    r8d, r8d
0x18000d118  jnz     short loc_18000D12A
0x18000d11a  mov     r8d, ebp
0x18000d11d  mov     edx, 3
0x18000d122  mov     rcx, rsi
0x18000d125  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d12a  test    byte ptr [rbx], 2
0x18000d12d  jnz     short loc_18000D153
0x18000d12f  mov     eax, [rbx]
0x18000d131  xor     eax, edi
0x18000d133  and     eax, 180h
0x18000d138  xor     eax, [rbx]
0x18000d13a  mov     ecx, eax
0x18000d13c  xor     ecx, edi
0x18000d13e  and     ecx, r15d
0x18000d141  xor     ecx, eax
0x18000d143  or      ecx, 1
0x18000d146  mov     eax, ecx
0x18000d148  xor     eax, edi
0x18000d14a  and     eax, 800h
0x18000d14f  xor     eax, ecx
0x18000d151  mov     [rbx], eax
0x18000d153  mov     rbp, [rsp+38h+arg_10]
0x18000d158  mov     rax, rbx
0x18000d15b  mov     rbx, [rsp+38h+arg_8]
0x18000d160  add     rsp, 20h
0x18000d164  pop     r15
0x18000d166  pop     rdi
0x18000d167  pop     rsi
0x18000d168  retn
```
