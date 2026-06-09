# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_24_08_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180014110`
- end: `0x18001427d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_24_08_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014320`

## callees

- `0x1800054b4`
- `0x18000a080`
- `0x180014110`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_24_08_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_24_08_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_24_08_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45034786, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_24_08_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_24_08_NonSec__descriptor, 3, v4);
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
0x180014110  mov     [rsp+arg_8], rbx
0x180014115  mov     [rsp+arg_10], rbp
0x18001411a  mov     [rsp+arg_0], rcx
0x18001411f  push    rsi
0x180014120  push    rdi
0x180014121  push    r15
0x180014123  sub     rsp, 20h
0x180014127  mov     rsi, cs:Feature_Standalone_24_08_NonSec__descriptor
0x18001412e  mov     rbx, rdx
0x180014131  mov     qword ptr [rdx], 0
0x180014138  mov     eax, [rsi]
0x18001413a  mov     [rdx], eax
0x18001413c  and     eax, 6
0x18001413f  cmp     al, 6
0x180014141  jz      loc_180014267
0x180014147  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001414c  mov     ebp, eax
0x18001414e  mov     dword ptr [rsp+38h+arg_0], 0
0x180014156  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001415d  test    rax, rax
0x180014160  jz      short loc_18001417A
0x180014162  lea     r8, [rsp+38h+arg_0]
0x180014167  mov     edx, 3
0x18001416c  mov     ecx, 2AF2D22h
0x180014171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014176  mov     edx, eax
0x180014178  jmp     short loc_180014188
0x18001417a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014181  test    rax, rax
0x180014184  jnz     short loc_180014162
0x180014186  xor     edx, edx
0x180014188  mov     r8d, edx
0x18001418b  mov     eax, edx
0x18001418d  and     r8d, 0FFFFFF3Fh
0x180014194  and     edx, 80h
0x18001419a  mov     ecx, r8d
0x18001419d  mov     r15d, 40h ; '@'
0x1800141a3  and     ecx, 3
0x1800141a6  and     eax, r15d
0x1800141a9  shl     ecx, 2
0x1800141ac  or      ecx, eax
0x1800141ae  shl     ecx, 2
0x1800141b1  or      ecx, edx
0x1800141b3  lea     edi, ds:0[rcx*8]
0x1800141ba  test    r8d, r8d
0x1800141bd  jnz     short loc_1800141C4
0x1800141bf  mov     eax, r15d
0x1800141c2  jmp     short loc_1800141CE
0x1800141c4  xor     eax, eax
0x1800141c6  cmp     r8d, 2
0x1800141ca  cmovz   eax, r15d
0x1800141ce  or      edi, eax
0x1800141d0  mov     eax, [rbx]
0x1800141d2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800141d7  mov     edx, eax
0x1800141d9  mov     [rbx], eax
0x1800141db  jz      short loc_180014207
0x1800141dd  test    dl, 2
0x1800141e0  jnz     short loc_180014207
0x1800141e2  xor     eax, edi
0x1800141e4  and     eax, 180h
0x1800141e9  xor     eax, edx
0x1800141eb  mov     ecx, eax
0x1800141ed  xor     ecx, edi
0x1800141ef  and     ecx, r15d
0x1800141f2  xor     ecx, eax
0x1800141f4  or      ecx, 1
0x1800141f7  mov     eax, ecx
0x1800141f9  xor     eax, edi
0x1800141fb  and     eax, 800h
0x180014200  xor     eax, ecx
0x180014202  or      eax, 2
0x180014205  mov     [rbx], eax
0x180014207  mov     r8d, edx
0x18001420a  mov     ecx, eax
0x18001420c  and     r8d, 4
0x180014210  jnz     short loc_180014221
0x180014212  xor     ecx, edi
0x180014214  and     ecx, 400h
0x18001421a  xor     ecx, eax
0x18001421c  or      ecx, 4
0x18001421f  mov     [rbx], ecx
0x180014221  mov     eax, edx
0x180014223  lock cmpxchg [rsi], ecx
0x180014227  jnz     short loc_1800141D2
0x180014229  test    r8d, r8d
0x18001422c  jnz     short loc_18001423E
0x18001422e  mov     r8d, ebp
0x180014231  mov     edx, 3
0x180014236  mov     rcx, rsi
0x180014239  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001423e  test    byte ptr [rbx], 2
0x180014241  jnz     short loc_180014267
0x180014243  mov     eax, [rbx]
0x180014245  xor     eax, edi
0x180014247  and     eax, 180h
0x18001424c  xor     eax, [rbx]
0x18001424e  mov     ecx, eax
0x180014250  xor     ecx, edi
0x180014252  and     ecx, r15d
0x180014255  xor     ecx, eax
0x180014257  or      ecx, 1
0x18001425a  mov     eax, ecx
0x18001425c  xor     eax, edi
0x18001425e  and     eax, 800h
0x180014263  xor     eax, ecx
0x180014265  mov     [rbx], eax
0x180014267  mov     rbp, [rsp+38h+arg_10]
0x18001426c  mov     rax, rbx
0x18001426f  mov     rbx, [rsp+38h+arg_8]
0x180014274  add     rsp, 20h
0x180014278  pop     r15
0x18001427a  pop     rdi
0x18001427b  pop     rsi
0x18001427c  retn
```
