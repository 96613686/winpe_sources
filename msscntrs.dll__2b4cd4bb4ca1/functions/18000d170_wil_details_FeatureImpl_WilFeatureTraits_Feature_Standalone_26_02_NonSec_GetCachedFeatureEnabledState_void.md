# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000d170`
- end: `0x18000d2dd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d544`
- `0x18000d6a4`
- `0x180012dd0`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000d170`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599550, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v4);
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
0x18000d170  mov     [rsp+arg_8], rbx
0x18000d175  mov     [rsp+arg_10], rbp
0x18000d17a  mov     [rsp+arg_0], rcx
0x18000d17f  push    rsi
0x18000d180  push    rdi
0x18000d181  push    r15
0x18000d183  sub     rsp, 20h
0x18000d187  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000d18e  mov     rbx, rdx
0x18000d191  mov     qword ptr [rdx], 0
0x18000d198  mov     eax, [rsi]
0x18000d19a  mov     [rdx], eax
0x18000d19c  and     eax, 6
0x18000d19f  cmp     al, 6
0x18000d1a1  jz      loc_18000D2C7
0x18000d1a7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000d1ac  mov     ebp, eax
0x18000d1ae  mov     dword ptr [rsp+38h+arg_0], 0
0x18000d1b6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d1bd  test    rax, rax
0x18000d1c0  jz      short loc_18000D1DA
0x18000d1c2  lea     r8, [rsp+38h+arg_0]
0x18000d1c7  mov     edx, 3
0x18000d1cc  mov     ecx, 37E287Eh
0x18000d1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d6  mov     edx, eax
0x18000d1d8  jmp     short loc_18000D1E8
0x18000d1da  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d1e1  test    rax, rax
0x18000d1e4  jnz     short loc_18000D1C2
0x18000d1e6  xor     edx, edx
0x18000d1e8  mov     r8d, edx
0x18000d1eb  mov     eax, edx
0x18000d1ed  and     r8d, 0FFFFFF3Fh
0x18000d1f4  and     edx, 80h
0x18000d1fa  mov     ecx, r8d
0x18000d1fd  mov     r15d, 40h ; '@'
0x18000d203  and     ecx, 3
0x18000d206  and     eax, r15d
0x18000d209  shl     ecx, 2
0x18000d20c  or      ecx, eax
0x18000d20e  shl     ecx, 2
0x18000d211  or      ecx, edx
0x18000d213  lea     edi, ds:0[rcx*8]
0x18000d21a  test    r8d, r8d
0x18000d21d  jnz     short loc_18000D224
0x18000d21f  mov     eax, r15d
0x18000d222  jmp     short loc_18000D22E
0x18000d224  xor     eax, eax
0x18000d226  cmp     r8d, 2
0x18000d22a  cmovz   eax, r15d
0x18000d22e  or      edi, eax
0x18000d230  mov     eax, [rbx]
0x18000d232  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000d237  mov     edx, eax
0x18000d239  mov     [rbx], eax
0x18000d23b  jz      short loc_18000D267
0x18000d23d  test    dl, 2
0x18000d240  jnz     short loc_18000D267
0x18000d242  xor     eax, edi
0x18000d244  and     eax, 180h
0x18000d249  xor     eax, edx
0x18000d24b  mov     ecx, eax
0x18000d24d  xor     ecx, edi
0x18000d24f  and     ecx, r15d
0x18000d252  xor     ecx, eax
0x18000d254  or      ecx, 1
0x18000d257  mov     eax, ecx
0x18000d259  xor     eax, edi
0x18000d25b  and     eax, 800h
0x18000d260  xor     eax, ecx
0x18000d262  or      eax, 2
0x18000d265  mov     [rbx], eax
0x18000d267  mov     r8d, edx
0x18000d26a  mov     ecx, eax
0x18000d26c  and     r8d, 4
0x18000d270  jnz     short loc_18000D281
0x18000d272  xor     ecx, edi
0x18000d274  and     ecx, 400h
0x18000d27a  xor     ecx, eax
0x18000d27c  or      ecx, 4
0x18000d27f  mov     [rbx], ecx
0x18000d281  mov     eax, edx
0x18000d283  lock cmpxchg [rsi], ecx
0x18000d287  jnz     short loc_18000D232
0x18000d289  test    r8d, r8d
0x18000d28c  jnz     short loc_18000D29E
0x18000d28e  mov     r8d, ebp
0x18000d291  mov     edx, 3
0x18000d296  mov     rcx, rsi
0x18000d299  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d29e  test    byte ptr [rbx], 2
0x18000d2a1  jnz     short loc_18000D2C7
0x18000d2a3  mov     eax, [rbx]
0x18000d2a5  xor     eax, edi
0x18000d2a7  and     eax, 180h
0x18000d2ac  xor     eax, [rbx]
0x18000d2ae  mov     ecx, eax
0x18000d2b0  xor     ecx, edi
0x18000d2b2  and     ecx, r15d
0x18000d2b5  xor     ecx, eax
0x18000d2b7  or      ecx, 1
0x18000d2ba  mov     eax, ecx
0x18000d2bc  xor     eax, edi
0x18000d2be  and     eax, 800h
0x18000d2c3  xor     eax, ecx
0x18000d2c5  mov     [rbx], eax
0x18000d2c7  mov     rbp, [rsp+38h+arg_10]
0x18000d2cc  mov     rax, rbx
0x18000d2cf  mov     rbx, [rsp+38h+arg_8]
0x18000d2d4  add     rsp, 20h
0x18000d2d8  pop     r15
0x18000d2da  pop     rdi
0x18000d2db  pop     rsi
0x18000d2dc  retn
```
