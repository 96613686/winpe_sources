# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001267c`
- end: `0x1800127e9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013220`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18001267c`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599553, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_03_NonSec__descriptor, 3, v4);
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
0x18001267c  mov     [rsp+arg_8], rbx
0x180012681  mov     [rsp+arg_10], rbp
0x180012686  mov     [rsp+arg_0], rcx
0x18001268b  push    rsi
0x18001268c  push    rdi
0x18001268d  push    r15
0x18001268f  sub     rsp, 20h
0x180012693  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18001269a  mov     rbx, rdx
0x18001269d  mov     qword ptr [rdx], 0
0x1800126a4  mov     eax, [rsi]
0x1800126a6  mov     [rdx], eax
0x1800126a8  and     eax, 6
0x1800126ab  cmp     al, 6
0x1800126ad  jz      loc_1800127D3
0x1800126b3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800126b8  mov     ebp, eax
0x1800126ba  mov     dword ptr [rsp+38h+arg_0], 0
0x1800126c2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800126c9  test    rax, rax
0x1800126cc  jz      short loc_1800126E6
0x1800126ce  lea     r8, [rsp+38h+arg_0]
0x1800126d3  mov     edx, 3
0x1800126d8  mov     ecx, 37E2881h
0x1800126dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126e2  mov     edx, eax
0x1800126e4  jmp     short loc_1800126F4
0x1800126e6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800126ed  test    rax, rax
0x1800126f0  jnz     short loc_1800126CE
0x1800126f2  xor     edx, edx
0x1800126f4  mov     r8d, edx
0x1800126f7  mov     eax, edx
0x1800126f9  and     r8d, 0FFFFFF3Fh
0x180012700  and     edx, 80h
0x180012706  mov     ecx, r8d
0x180012709  mov     r15d, 40h ; '@'
0x18001270f  and     ecx, 3
0x180012712  and     eax, r15d
0x180012715  shl     ecx, 2
0x180012718  or      ecx, eax
0x18001271a  shl     ecx, 2
0x18001271d  or      ecx, edx
0x18001271f  lea     edi, ds:0[rcx*8]
0x180012726  test    r8d, r8d
0x180012729  jnz     short loc_180012730
0x18001272b  mov     eax, r15d
0x18001272e  jmp     short loc_18001273A
0x180012730  xor     eax, eax
0x180012732  cmp     r8d, 2
0x180012736  cmovz   eax, r15d
0x18001273a  or      edi, eax
0x18001273c  mov     eax, [rbx]
0x18001273e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012743  mov     edx, eax
0x180012745  mov     [rbx], eax
0x180012747  jz      short loc_180012773
0x180012749  test    dl, 2
0x18001274c  jnz     short loc_180012773
0x18001274e  xor     eax, edi
0x180012750  and     eax, 180h
0x180012755  xor     eax, edx
0x180012757  mov     ecx, eax
0x180012759  xor     ecx, edi
0x18001275b  and     ecx, r15d
0x18001275e  xor     ecx, eax
0x180012760  or      ecx, 1
0x180012763  mov     eax, ecx
0x180012765  xor     eax, edi
0x180012767  and     eax, 800h
0x18001276c  xor     eax, ecx
0x18001276e  or      eax, 2
0x180012771  mov     [rbx], eax
0x180012773  mov     r8d, edx
0x180012776  mov     ecx, eax
0x180012778  and     r8d, 4
0x18001277c  jnz     short loc_18001278D
0x18001277e  xor     ecx, edi
0x180012780  and     ecx, 400h
0x180012786  xor     ecx, eax
0x180012788  or      ecx, 4
0x18001278b  mov     [rbx], ecx
0x18001278d  mov     eax, edx
0x18001278f  lock cmpxchg [rsi], ecx
0x180012793  jnz     short loc_18001273E
0x180012795  test    r8d, r8d
0x180012798  jnz     short loc_1800127AA
0x18001279a  mov     r8d, ebp
0x18001279d  mov     edx, 3
0x1800127a2  mov     rcx, rsi
0x1800127a5  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800127aa  test    byte ptr [rbx], 2
0x1800127ad  jnz     short loc_1800127D3
0x1800127af  mov     eax, [rbx]
0x1800127b1  xor     eax, edi
0x1800127b3  and     eax, 180h
0x1800127b8  xor     eax, [rbx]
0x1800127ba  mov     ecx, eax
0x1800127bc  xor     ecx, edi
0x1800127be  and     ecx, r15d
0x1800127c1  xor     ecx, eax
0x1800127c3  or      ecx, 1
0x1800127c6  mov     eax, ecx
0x1800127c8  xor     eax, edi
0x1800127ca  and     eax, 800h
0x1800127cf  xor     eax, ecx
0x1800127d1  mov     [rbx], eax
0x1800127d3  mov     rbp, [rsp+38h+arg_10]
0x1800127d8  mov     rax, rbx
0x1800127db  mov     rbx, [rsp+38h+arg_8]
0x1800127e0  add     rsp, 20h
0x1800127e4  pop     r15
0x1800127e6  pop     rdi
0x1800127e7  pop     rsi
0x1800127e8  retn
```
