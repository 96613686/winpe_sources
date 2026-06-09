# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(void)

- ea: `0x18000a11c`
- end: `0x18000a289`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ffb0`
- `0x180010db0`
- `0x180011f20`

## callees

- `0x180009ca8`
- `0x18000a11c`
- `0x18000f31c`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AADPinResetV2__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AADPinResetV2__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(39729128, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_AADPinResetV2__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_AADPinResetV2__descriptor, 3, v4);
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
0x18000a11c  mov     [rsp+arg_8], rbx
0x18000a121  mov     [rsp+arg_10], rbp
0x18000a126  mov     [rsp+arg_0], rcx
0x18000a12b  push    rsi
0x18000a12c  push    rdi
0x18000a12d  push    r15
0x18000a12f  sub     rsp, 20h
0x18000a133  mov     rsi, cs:Feature_AADPinResetV2__descriptor
0x18000a13a  mov     rbx, rdx
0x18000a13d  mov     qword ptr [rdx], 0
0x18000a144  mov     eax, [rsi]
0x18000a146  mov     [rdx], eax
0x18000a148  and     eax, 6
0x18000a14b  cmp     al, 6
0x18000a14d  jz      loc_18000A273
0x18000a153  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a158  mov     ebp, eax
0x18000a15a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000a162  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000a169  test    rax, rax
0x18000a16c  jz      short loc_18000A186
0x18000a16e  lea     r8, [rsp+38h+arg_0]
0x18000a173  mov     edx, 3
0x18000a178  mov     ecx, 25E37E8h
0x18000a17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a182  mov     edx, eax
0x18000a184  jmp     short loc_18000A194
0x18000a186  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000a18d  test    rax, rax
0x18000a190  jnz     short loc_18000A16E
0x18000a192  xor     edx, edx
0x18000a194  mov     r8d, edx
0x18000a197  mov     eax, edx
0x18000a199  and     r8d, 0FFFFFF3Fh
0x18000a1a0  and     edx, 80h
0x18000a1a6  mov     ecx, r8d
0x18000a1a9  mov     r15d, 40h ; '@'
0x18000a1af  and     ecx, 3
0x18000a1b2  and     eax, r15d
0x18000a1b5  shl     ecx, 2
0x18000a1b8  or      ecx, eax
0x18000a1ba  shl     ecx, 2
0x18000a1bd  or      ecx, edx
0x18000a1bf  lea     edi, ds:0[rcx*8]
0x18000a1c6  test    r8d, r8d
0x18000a1c9  jnz     short loc_18000A1D0
0x18000a1cb  mov     eax, r15d
0x18000a1ce  jmp     short loc_18000A1DA
0x18000a1d0  xor     eax, eax
0x18000a1d2  cmp     r8d, 2
0x18000a1d6  cmovz   eax, r15d
0x18000a1da  or      edi, eax
0x18000a1dc  mov     eax, [rbx]
0x18000a1de  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000a1e3  mov     edx, eax
0x18000a1e5  mov     [rbx], eax
0x18000a1e7  jz      short loc_18000A213
0x18000a1e9  test    dl, 2
0x18000a1ec  jnz     short loc_18000A213
0x18000a1ee  xor     eax, edi
0x18000a1f0  and     eax, 180h
0x18000a1f5  xor     eax, edx
0x18000a1f7  mov     ecx, eax
0x18000a1f9  xor     ecx, edi
0x18000a1fb  and     ecx, r15d
0x18000a1fe  xor     ecx, eax
0x18000a200  or      ecx, 1
0x18000a203  mov     eax, ecx
0x18000a205  xor     eax, edi
0x18000a207  and     eax, 800h
0x18000a20c  xor     eax, ecx
0x18000a20e  or      eax, 2
0x18000a211  mov     [rbx], eax
0x18000a213  mov     r8d, edx
0x18000a216  mov     ecx, eax
0x18000a218  and     r8d, 4
0x18000a21c  jnz     short loc_18000A22D
0x18000a21e  xor     ecx, edi
0x18000a220  and     ecx, 400h
0x18000a226  xor     ecx, eax
0x18000a228  or      ecx, 4
0x18000a22b  mov     [rbx], ecx
0x18000a22d  mov     eax, edx
0x18000a22f  lock cmpxchg [rsi], ecx
0x18000a233  jnz     short loc_18000A1DE
0x18000a235  test    r8d, r8d
0x18000a238  jnz     short loc_18000A24A
0x18000a23a  mov     r8d, ebp
0x18000a23d  mov     edx, 3
0x18000a242  mov     rcx, rsi
0x18000a245  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a24a  test    byte ptr [rbx], 2
0x18000a24d  jnz     short loc_18000A273
0x18000a24f  mov     eax, [rbx]
0x18000a251  xor     eax, edi
0x18000a253  and     eax, 180h
0x18000a258  xor     eax, [rbx]
0x18000a25a  mov     ecx, eax
0x18000a25c  xor     ecx, edi
0x18000a25e  and     ecx, r15d
0x18000a261  xor     ecx, eax
0x18000a263  or      ecx, 1
0x18000a266  mov     eax, ecx
0x18000a268  xor     eax, edi
0x18000a26a  and     eax, 800h
0x18000a26f  xor     eax, ecx
0x18000a271  mov     [rbx], eax
0x18000a273  mov     rbp, [rsp+38h+arg_10]
0x18000a278  mov     rax, rbx
0x18000a27b  mov     rbx, [rsp+38h+arg_8]
0x18000a280  add     rsp, 20h
0x18000a284  pop     r15
0x18000a286  pop     rdi
0x18000a287  pop     rsi
0x18000a288  retn
```
