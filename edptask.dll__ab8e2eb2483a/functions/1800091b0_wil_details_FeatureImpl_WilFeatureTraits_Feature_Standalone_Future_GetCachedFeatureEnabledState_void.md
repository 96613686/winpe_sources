# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x1800091b0`
- end: `0x180009327`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c14`

## callees

- `0x1800084b4`
- `0x1800091b0`
- `0x1800113c4`
- `0x180014010`

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
0x1800091b0  mov     [rsp+arg_8], rbx
0x1800091b5  mov     [rsp+arg_10], rbp
0x1800091ba  mov     [rsp+arg_0], rcx
0x1800091bf  push    rsi
0x1800091c0  push    rdi
0x1800091c1  push    r15
0x1800091c3  sub     rsp, 20h
0x1800091c7  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x1800091ce  mov     rbx, rdx
0x1800091d1  mov     qword ptr [rdx], 0
0x1800091d8  mov     eax, [rsi]
0x1800091da  mov     [rdx], eax
0x1800091dc  and     eax, 6
0x1800091df  cmp     al, 6
0x1800091e1  jz      loc_180009311
0x1800091e7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800091ec  mov     ebp, eax
0x1800091ee  mov     dword ptr [rsp+38h+arg_0], 0
0x1800091f6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800091fd  test    rax, rax
0x180009200  jz      short loc_18000921A
0x180009202  lea     r8, [rsp+38h+arg_0]
0x180009207  mov     edx, 3
0x18000920c  mov     ecx, 2F29A04h
0x180009211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009216  mov     edx, eax
0x180009218  jmp     short loc_180009228
0x18000921a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009221  test    rax, rax
0x180009224  jnz     short loc_180009202
0x180009226  xor     edx, edx
0x180009228  mov     r8d, edx
0x18000922b  mov     eax, edx
0x18000922d  and     r8d, 0FFFFFF3Fh
0x180009234  and     edx, 80h
0x18000923a  mov     ecx, r8d
0x18000923d  mov     r15d, 40h ; '@'
0x180009243  and     ecx, 3
0x180009246  and     eax, r15d
0x180009249  shl     ecx, 2
0x18000924c  or      ecx, eax
0x18000924e  shl     ecx, 2
0x180009251  or      ecx, edx
0x180009253  lea     edi, ds:0[rcx*8]
0x18000925a  test    r8d, r8d
0x18000925d  jnz     short loc_180009264
0x18000925f  mov     eax, r15d
0x180009262  jmp     short loc_18000926E
0x180009264  xor     eax, eax
0x180009266  cmp     r8d, 2
0x18000926a  cmovz   eax, r15d
0x18000926e  or      edi, eax
0x180009270  mov     eax, [rbx]
0x180009272  cmp     dword ptr [rsp+38h+arg_0], 0
0x180009277  mov     edx, eax
0x180009279  mov     [rbx], eax
0x18000927b  jz      short loc_1800092AB
0x18000927d  test    dl, 2
0x180009280  jnz     short loc_1800092AB
0x180009282  mov     eax, edi
0x180009284  xor     eax, edx
0x180009286  and     eax, 180h
0x18000928b  xor     eax, edx
0x18000928d  mov     ecx, eax
0x18000928f  xor     ecx, edi
0x180009291  and     ecx, r15d
0x180009294  xor     ecx, eax
0x180009296  or      ecx, 1
0x180009299  mov     eax, ecx
0x18000929b  xor     eax, edi
0x18000929d  and     eax, 800h
0x1800092a2  xor     eax, ecx
0x1800092a4  or      eax, 2
0x1800092a7  mov     [rbx], eax
0x1800092a9  jmp     short loc_1800092AD
0x1800092ab  mov     eax, edx
0x1800092ad  mov     r8d, edx
0x1800092b0  and     r8d, 4
0x1800092b4  jnz     short loc_1800092C9
0x1800092b6  mov     ecx, edi
0x1800092b8  xor     ecx, eax
0x1800092ba  and     ecx, 400h
0x1800092c0  xor     ecx, eax
0x1800092c2  or      ecx, 4
0x1800092c5  mov     [rbx], ecx
0x1800092c7  jmp     short loc_1800092CB
0x1800092c9  mov     ecx, eax
0x1800092cb  mov     eax, edx
0x1800092cd  lock cmpxchg [rsi], ecx
0x1800092d1  jnz     short loc_180009272
0x1800092d3  test    r8d, r8d
0x1800092d6  jnz     short loc_1800092E8
0x1800092d8  mov     r8d, ebp
0x1800092db  mov     edx, 3
0x1800092e0  mov     rcx, rsi
0x1800092e3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800092e8  test    byte ptr [rbx], 2
0x1800092eb  jnz     short loc_180009311
0x1800092ed  mov     eax, [rbx]
0x1800092ef  xor     eax, edi
0x1800092f1  and     eax, 180h
0x1800092f6  xor     eax, [rbx]
0x1800092f8  mov     ecx, eax
0x1800092fa  xor     ecx, edi
0x1800092fc  and     ecx, r15d
0x1800092ff  xor     ecx, eax
0x180009301  or      ecx, 1
0x180009304  mov     eax, ecx
0x180009306  xor     eax, edi
0x180009308  and     eax, 800h
0x18000930d  xor     eax, ecx
0x18000930f  mov     [rbx], eax
0x180009311  mov     rbp, [rsp+38h+arg_10]
0x180009316  mov     rax, rbx
0x180009319  mov     rbx, [rsp+38h+arg_8]
0x18000931e  add     rsp, 20h
0x180009322  pop     r15
0x180009324  pop     rdi
0x180009325  pop     rsi
0x180009326  retn
```
