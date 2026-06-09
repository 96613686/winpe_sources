# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180024120`
- end: `0x18002429f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxConfTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029460`

## callees

- `0x18001e1d0`
- `0x1800239b0`
- `0x180024120`
- `0x180028210`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  __int16 v2; // di
  int v4; // eax
  int v5; // ebp
  __int64 (__fastcall *v6)(__int64, __int64, int *); // rax
  int v7; // eax
  __int16 v8; // cx
  unsigned __int16 v9; // di
  int v10; // eax
  bool v11; // zf
  signed __int32 v12; // edx
  signed __int32 v13; // ecx
  int v14; // eax
  int v16; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  *a2 = 0;
  v4 = *(_DWORD *)Feature_UxConfTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxConfTest__descriptor;
  if ( (v4 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v16 = 0;
  v6 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(50557073, 3, &v16);
    v8 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      if ( (v7 & 0xFFFFFF3F) == 2 )
        v2 = 64;
      v9 = v8 | v2;
      goto LABEL_10;
    }
  }
  else
  {
    v8 = 0;
  }
  v9 = v8 | 0x40;
LABEL_10:
  v10 = *(_DWORD *)a2;
  do
  {
    v11 = v16 == 0;
    v12 = v10;
    *(_DWORD *)a2 = v10;
    if ( !v11 && (v10 & 2) == 0 )
    {
      v10 = (v10
           ^ (v9
            ^ (unsigned __int16)v10)
           & 0x180
           ^ ((unsigned __int8)v9
            ^ (unsigned __int8)(v10 ^ (v9 ^ v10) & 0x80))
           & 0x40
           | 1)
          ^ (v9
           ^ ((unsigned __int16)(v10
                               ^ (v9
                                ^ v10)
                               & 0x180
                               ^ ((unsigned __int8)v9
                                ^ (unsigned __int8)(v10 ^ (v9 ^ v10) & 0x80))
                               & 0x40)
            | 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v10;
    }
    v13 = v10;
    if ( (v12 & 4) == 0 )
    {
      v13 = v10 ^ (v9 ^ (unsigned __int16)v10) & 0x400 | 4;
      *(_DWORD *)a2 = v13;
    }
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxConfTest__descriptor, v13, v12);
  }
  while ( v12 != v10 );
  if ( (v12 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_UxConfTest__descriptor,
      3u,
      v5);
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v14 = *(_DWORD *)a2;
    *(_DWORD *)a2 = (v14
                   ^ (v9
                    ^ (unsigned __int16)v14)
                   & 0x180
                   ^ ((unsigned __int8)v9
                    ^ (unsigned __int8)(v14 ^ (v9 ^ v14) & 0x80))
                   & 0x40
                   | 1)
                  ^ (v9
                   ^ ((unsigned __int16)(v14
                                       ^ (v9
                                        ^ v14)
                                       & 0x180
                                       ^ ((unsigned __int8)v9
                                        ^ (unsigned __int8)(v14 ^ (v9 ^ v14) & 0x80))
                                       & 0x40)
                    | 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180024120  mov     [rsp+arg_10], rbx
0x180024125  mov     [rsp+arg_18], rsi
0x18002412a  push    rdi
0x18002412b  sub     rsp, 30h
0x18002412f  mov     rax, cs:__security_cookie
0x180024136  xor     rax, rsp
0x180024139  mov     [rsp+38h+var_10], rax
0x18002413e  mov     rsi, cs:Feature_UxConfTest__descriptor
0x180024145  xor     edi, edi
0x180024147  mov     [rdx], rdi
0x18002414a  mov     rbx, rdx
0x18002414d  mov     eax, [rsi]
0x18002414f  mov     [rdx], eax
0x180024151  and     eax, 6
0x180024154  cmp     al, 6
0x180024156  jz      loc_18002427F
0x18002415c  mov     [rsp+38h+arg_0], rbp
0x180024161  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180024166  mov     ebp, eax
0x180024168  mov     [rsp+38h+var_18], edi
0x18002416c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180024173  test    rax, rax
0x180024176  jnz     short loc_180024184
0x180024178  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002417f  test    rax, rax
0x180024182  jz      short loc_1800241D9
0x180024184  lea     r8, [rsp+38h+var_18]
0x180024189  mov     edx, 3
0x18002418e  mov     ecx, 3037091h
0x180024193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024198  mov     r8d, eax
0x18002419b  mov     edx, eax
0x18002419d  and     r8d, 0FFFFFF3Fh
0x1800241a4  and     eax, 40h
0x1800241a7  and     edx, 80h
0x1800241ad  mov     ecx, r8d
0x1800241b0  and     ecx, 3
0x1800241b3  shl     ecx, 2
0x1800241b6  or      ecx, eax
0x1800241b8  shl     ecx, 2
0x1800241bb  or      ecx, edx
0x1800241bd  lea     ecx, ds:0[rcx*8]
0x1800241c4  test    r8d, r8d
0x1800241c7  jz      short loc_1800241DB
0x1800241c9  cmp     r8d, 2
0x1800241cd  mov     eax, 40h ; '@'
0x1800241d2  cmovz   edi, eax
0x1800241d5  or      edi, ecx
0x1800241d7  jmp     short loc_1800241E0
0x1800241d9  mov     ecx, edi
0x1800241db  mov     edi, ecx
0x1800241dd  or      edi, 40h
0x1800241e0  mov     eax, [rbx]
0x1800241e2  cmp     [rsp+38h+var_18], 0
0x1800241e7  mov     edx, eax
0x1800241e9  mov     [rbx], eax
0x1800241eb  jz      short loc_180024217
0x1800241ed  test    dl, 2
0x1800241f0  jnz     short loc_180024217
0x1800241f2  xor     eax, edi
0x1800241f4  and     eax, 180h
0x1800241f9  xor     eax, edx
0x1800241fb  mov     ecx, eax
0x1800241fd  xor     ecx, edi
0x1800241ff  and     ecx, 40h
0x180024202  xor     ecx, eax
0x180024204  or      ecx, 1
0x180024207  mov     eax, ecx
0x180024209  xor     eax, edi
0x18002420b  and     eax, 800h
0x180024210  xor     eax, ecx
0x180024212  or      eax, 2
0x180024215  mov     [rbx], eax
0x180024217  mov     r8d, edx
0x18002421a  mov     ecx, eax
0x18002421c  and     r8d, 4
0x180024220  jnz     short loc_180024231
0x180024222  xor     ecx, edi
0x180024224  and     ecx, 400h
0x18002422a  xor     ecx, eax
0x18002422c  or      ecx, 4
0x18002422f  mov     [rbx], ecx
0x180024231  mov     eax, edx
0x180024233  lock cmpxchg [rsi], ecx
0x180024237  jnz     short loc_1800241E2
0x180024239  test    r8d, r8d
0x18002423c  jnz     short loc_18002424E
0x18002423e  mov     r8d, ebp
0x180024241  mov     edx, 3
0x180024246  mov     rcx, rsi
0x180024249  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002424e  mov     eax, [rbx]
0x180024250  mov     rbp, [rsp+38h+arg_0]
0x180024255  test    al, 2
0x180024257  jnz     short loc_18002427F
0x180024259  mov     ecx, eax
0x18002425b  xor     ecx, edi
0x18002425d  and     ecx, 180h
0x180024263  xor     ecx, eax
0x180024265  mov     edx, ecx
0x180024267  xor     edx, edi
0x180024269  and     edx, 40h
0x18002426c  xor     edx, ecx
0x18002426e  or      edx, 1
0x180024271  mov     ecx, edx
0x180024273  xor     ecx, edi
0x180024275  and     ecx, 800h
0x18002427b  xor     ecx, edx
0x18002427d  mov     [rbx], ecx
0x18002427f  mov     rax, rbx
0x180024282  mov     rcx, [rsp+38h+var_10]
0x180024287  xor     rcx, rsp; StackCookie
0x18002428a  call    __security_check_cookie
0x18002428f  mov     rbx, [rsp+38h+arg_10]
0x180024294  mov     rsi, [rsp+38h+arg_18]
0x180024299  add     rsp, 30h
0x18002429d  pop     rdi
0x18002429e  retn
```
