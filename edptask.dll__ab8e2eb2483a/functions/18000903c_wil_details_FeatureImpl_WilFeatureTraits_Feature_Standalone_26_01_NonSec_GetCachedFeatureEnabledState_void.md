# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000903c`
- end: `0x1800091a9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009aa4`

## callees

- `0x1800084b4`
- `0x18000903c`
- `0x1800113c4`
- `0x180014010`

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
0x18000903c  mov     [rsp+arg_8], rbx
0x180009041  mov     [rsp+arg_10], rbp
0x180009046  mov     [rsp+arg_0], rcx
0x18000904b  push    rsi
0x18000904c  push    rdi
0x18000904d  push    r15
0x18000904f  sub     rsp, 20h
0x180009053  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000905a  mov     rbx, rdx
0x18000905d  mov     qword ptr [rdx], 0
0x180009064  mov     eax, [rsi]
0x180009066  mov     [rdx], eax
0x180009068  and     eax, 6
0x18000906b  cmp     al, 6
0x18000906d  jz      loc_180009193
0x180009073  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009078  mov     ebp, eax
0x18000907a  mov     dword ptr [rsp+38h+arg_0], 0
0x180009082  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009089  test    rax, rax
0x18000908c  jz      short loc_1800090A6
0x18000908e  lea     r8, [rsp+38h+arg_0]
0x180009093  mov     edx, 3
0x180009098  mov     ecx, 37E286Ch
0x18000909d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a2  mov     edx, eax
0x1800090a4  jmp     short loc_1800090B4
0x1800090a6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800090ad  test    rax, rax
0x1800090b0  jnz     short loc_18000908E
0x1800090b2  xor     edx, edx
0x1800090b4  mov     r8d, edx
0x1800090b7  mov     eax, edx
0x1800090b9  and     r8d, 0FFFFFF3Fh
0x1800090c0  and     edx, 80h
0x1800090c6  mov     ecx, r8d
0x1800090c9  mov     r15d, 40h ; '@'
0x1800090cf  and     ecx, 3
0x1800090d2  and     eax, r15d
0x1800090d5  shl     ecx, 2
0x1800090d8  or      ecx, eax
0x1800090da  shl     ecx, 2
0x1800090dd  or      ecx, edx
0x1800090df  lea     edi, ds:0[rcx*8]
0x1800090e6  test    r8d, r8d
0x1800090e9  jnz     short loc_1800090F0
0x1800090eb  mov     eax, r15d
0x1800090ee  jmp     short loc_1800090FA
0x1800090f0  xor     eax, eax
0x1800090f2  cmp     r8d, 2
0x1800090f6  cmovz   eax, r15d
0x1800090fa  or      edi, eax
0x1800090fc  mov     eax, [rbx]
0x1800090fe  cmp     dword ptr [rsp+38h+arg_0], 0
0x180009103  mov     edx, eax
0x180009105  mov     [rbx], eax
0x180009107  jz      short loc_180009133
0x180009109  test    dl, 2
0x18000910c  jnz     short loc_180009133
0x18000910e  xor     eax, edi
0x180009110  and     eax, 180h
0x180009115  xor     eax, edx
0x180009117  mov     ecx, eax
0x180009119  xor     ecx, edi
0x18000911b  and     ecx, r15d
0x18000911e  xor     ecx, eax
0x180009120  or      ecx, 1
0x180009123  mov     eax, ecx
0x180009125  xor     eax, edi
0x180009127  and     eax, 800h
0x18000912c  xor     eax, ecx
0x18000912e  or      eax, 2
0x180009131  mov     [rbx], eax
0x180009133  mov     r8d, edx
0x180009136  mov     ecx, eax
0x180009138  and     r8d, 4
0x18000913c  jnz     short loc_18000914D
0x18000913e  xor     ecx, edi
0x180009140  and     ecx, 400h
0x180009146  xor     ecx, eax
0x180009148  or      ecx, 4
0x18000914b  mov     [rbx], ecx
0x18000914d  mov     eax, edx
0x18000914f  lock cmpxchg [rsi], ecx
0x180009153  jnz     short loc_1800090FE
0x180009155  test    r8d, r8d
0x180009158  jnz     short loc_18000916A
0x18000915a  mov     r8d, ebp
0x18000915d  mov     edx, 3
0x180009162  mov     rcx, rsi
0x180009165  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000916a  test    byte ptr [rbx], 2
0x18000916d  jnz     short loc_180009193
0x18000916f  mov     eax, [rbx]
0x180009171  xor     eax, edi
0x180009173  and     eax, 180h
0x180009178  xor     eax, [rbx]
0x18000917a  mov     ecx, eax
0x18000917c  xor     ecx, edi
0x18000917e  and     ecx, r15d
0x180009181  xor     ecx, eax
0x180009183  or      ecx, 1
0x180009186  mov     eax, ecx
0x180009188  xor     eax, edi
0x18000918a  and     eax, 800h
0x18000918f  xor     eax, ecx
0x180009191  mov     [rbx], eax
0x180009193  mov     rbp, [rsp+38h+arg_10]
0x180009198  mov     rax, rbx
0x18000919b  mov     rbx, [rsp+38h+arg_8]
0x1800091a0  add     rsp, 20h
0x1800091a4  pop     r15
0x1800091a6  pop     rdi
0x1800091a7  pop     rsi
0x1800091a8  retn
```
