# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::GetCachedFeatureEnabledState(void)

- ea: `0x180023f10`
- end: `0x18002410f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800293a0`

## callees

- `0x18001e1d0`
- `0x1800239b0`
- `0x180023f10`
- `0x180028210`
- `0x180029460`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, int *); // rax
  int v6; // eax
  unsigned int v7; // r8d
  __int16 v8; // di
  __int16 v9; // ax
  __int16 v10; // di
  char v11; // al
  __int16 v12; // ax
  unsigned __int16 v13; // di
  signed __int32 v14; // eax
  bool v15; // zf
  signed __int32 v16; // r8d
  int v17; // edx
  int v18; // r9d
  signed __int32 v19; // ecx
  int v20; // ecx
  int v22; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Firewall_042024__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Firewall_042024__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v22 = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      v8 = 0;
      goto LABEL_9;
    }
  }
  v6 = v5(49454120, 3, &v22);
  v7 = v6 & 0xFFFFFF3F;
  v8 = 8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3)))));
  if ( (v6 & 0xFFFFFF3F) == 0 )
  {
LABEL_9:
    v9 = 64;
    goto LABEL_10;
  }
  v9 = 0;
  if ( v7 == 2 )
    v9 = 64;
LABEL_10:
  v10 = v9 | v8;
  if ( (v10 & 0xC00) == 0xC00 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_UxConfTest>::GetImpl'::`2'::impl);
    v11 = 1;
  }
  else
  {
    if ( (v10 & 0x40) != 0 )
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_UxConfTest>::GetImpl'::`2'::impl);
      v12 = 1;
      goto LABEL_19;
    }
    v11 = 0;
  }
  v12 = (v10 & 0x40) != 0 && v11;
LABEL_19:
  v13 = v12 | v10;
  v14 = *(_DWORD *)a2;
  do
  {
    v15 = v22 == 0;
    v16 = v14;
    *(_DWORD *)a2 = v14;
    if ( v15 || (v14 & 2) != 0 )
    {
      v17 = v14;
    }
    else
    {
      v17 = v14
          ^ ((unsigned __int16)v14
           ^ v13)
          & 0x180
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80))
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80 ^ (v13 ^ v14 ^ (v14 ^ v13) & 0x80) & 0x40))
          & 1
          ^ (v13
           ^ (unsigned __int16)(v14
                              ^ (v14
                               ^ v13)
                              & 0x180
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80))
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80 ^ (v13 ^ v14 ^ (v14 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v17;
    }
    v18 = v14 & 4;
    if ( (v14 & 4) != 0 )
    {
      v19 = v17;
    }
    else
    {
      v19 = v17 ^ ((unsigned __int16)v17 ^ v13) & 0x400 | 4;
      *(_DWORD *)a2 = v19;
    }
    v14 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Firewall_042024__descriptor, v19, v14);
  }
  while ( v16 != v14 );
  if ( !v18 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Firewall_042024__descriptor,
      3u,
      v4);
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v20 = *(_DWORD *)a2
        ^ (v13
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v13
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v13 ^ *(_DWORD *)a2) & 0x80))
        & 0x40;
    *(_DWORD *)a2 = v20
                  ^ ((unsigned __int8)v13
                   ^ (unsigned __int8)v20)
                  & 1
                  ^ (v13
                   ^ (unsigned __int16)(v20 ^ ((unsigned __int8)v13 ^ (unsigned __int8)v20) & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180023f10  push    rbx
0x180023f12  push    r14
0x180023f14  sub     rsp, 38h
0x180023f18  mov     rax, cs:__security_cookie
0x180023f1f  xor     rax, rsp
0x180023f22  mov     [rsp+48h+var_20], rax
0x180023f27  mov     r14, cs:Feature_Firewall_042024__descriptor
0x180023f2e  mov     rbx, rdx
0x180023f31  mov     qword ptr [rdx], 0
0x180023f38  mov     eax, [r14]
0x180023f3b  mov     [rdx], eax
0x180023f3d  and     eax, 6
0x180023f40  cmp     al, 6
0x180023f42  jz      loc_18002410A
0x180023f48  mov     [rsp+48h+arg_0], rbp
0x180023f4d  mov     [rsp+48h+arg_10], rsi
0x180023f52  mov     [rsp+48h+var_18], rdi
0x180023f57  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180023f5c  mov     ebp, eax
0x180023f5e  mov     [rsp+48h+var_28], 0
0x180023f66  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180023f6d  test    rax, rax
0x180023f70  jnz     short loc_180023F7E
0x180023f72  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180023f79  test    rax, rax
0x180023f7c  jz      short loc_180023FD3
0x180023f7e  lea     r8, [rsp+48h+var_28]
0x180023f83  mov     edx, 3
0x180023f88  mov     ecx, 2F29C28h
0x180023f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f92  mov     r8d, eax
0x180023f95  mov     edx, eax
0x180023f97  and     r8d, 0FFFFFF3Fh
0x180023f9e  and     eax, 40h
0x180023fa1  and     edx, 80h
0x180023fa7  mov     ecx, r8d
0x180023faa  and     ecx, 3
0x180023fad  shl     ecx, 2
0x180023fb0  or      ecx, eax
0x180023fb2  shl     ecx, 2
0x180023fb5  or      ecx, edx
0x180023fb7  lea     edi, ds:0[rcx*8]
0x180023fbe  test    r8d, r8d
0x180023fc1  jz      short loc_180023FD5
0x180023fc3  xor     eax, eax
0x180023fc5  mov     ecx, 40h ; '@'
0x180023fca  cmp     r8d, 2
0x180023fce  cmovz   eax, ecx
0x180023fd1  jmp     short loc_180023FDA
0x180023fd3  xor     edi, edi
0x180023fd5  mov     eax, 40h ; '@'
0x180023fda  or      edi, eax
0x180023fdc  mov     esi, edi
0x180023fde  mov     eax, edi
0x180023fe0  and     esi, 40h
0x180023fe3  and     eax, 0C00h
0x180023fe8  cmp     eax, 0C00h
0x180023fed  jnz     short loc_180023FFF
0x180023fef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxConfTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxConfTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest> `wil::Feature<__WilFeatureTraits_Feature_UxConfTest>::GetImpl(void)'::`2'::impl
0x180023ff6  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_UxConfTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180023ffb  mov     al, 1
0x180023ffd  jmp     short loc_180024018
0x180023fff  test    esi, esi
0x180024001  jz      short loc_180024016
0x180024003  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxConfTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxConfTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest> `wil::Feature<__WilFeatureTraits_Feature_UxConfTest>::GetImpl(void)'::`2'::impl
0x18002400a  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_UxConfTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxConfTest>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18002400f  mov     eax, 1
0x180024014  jmp     short loc_180024029
0x180024016  xor     al, al
0x180024018  test    esi, esi
0x18002401a  jz      short loc_180024027
0x18002401c  test    al, al
0x18002401e  jz      short loc_180024027
0x180024020  mov     eax, 1
0x180024025  jmp     short loc_180024029
0x180024027  xor     eax, eax
0x180024029  mov     rsi, [rsp+48h+arg_10]
0x18002402e  or      edi, eax
0x180024030  mov     eax, [rbx]
0x180024032  cmp     [rsp+48h+var_28], 0
0x180024037  mov     r8d, eax
0x18002403a  mov     [rbx], eax
0x18002403c  jz      short loc_180024076
0x18002403e  test    r8b, 2
0x180024042  jnz     short loc_180024076
0x180024044  mov     eax, edi
0x180024046  xor     eax, r8d
0x180024049  and     eax, 180h
0x18002404e  xor     eax, r8d
0x180024051  mov     ecx, eax
0x180024053  xor     ecx, edi
0x180024055  and     ecx, 40h
0x180024058  xor     ecx, eax
0x18002405a  mov     eax, ecx
0x18002405c  xor     eax, edi
0x18002405e  and     eax, 1
0x180024061  xor     eax, ecx
0x180024063  mov     edx, eax
0x180024065  xor     edx, edi
0x180024067  and     edx, 800h
0x18002406d  xor     edx, eax
0x18002406f  or      edx, 2
0x180024072  mov     [rbx], edx
0x180024074  jmp     short loc_180024079
0x180024076  mov     edx, r8d
0x180024079  mov     r9d, r8d
0x18002407c  and     r9d, 4
0x180024080  jnz     short loc_180024095
0x180024082  mov     ecx, edi
0x180024084  xor     ecx, edx
0x180024086  and     ecx, 400h
0x18002408c  xor     ecx, edx
0x18002408e  or      ecx, 4
0x180024091  mov     [rbx], ecx
0x180024093  jmp     short loc_180024097
0x180024095  mov     ecx, edx
0x180024097  mov     eax, r8d
0x18002409a  lock cmpxchg [r14], ecx
0x18002409f  jnz     short loc_180024032
0x1800240a1  test    r9d, r9d
0x1800240a4  jnz     short loc_1800240B6
0x1800240a6  mov     r8d, ebp
0x1800240a9  mov     edx, 3
0x1800240ae  mov     rcx, r14
0x1800240b1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800240b6  mov     ecx, [rbx]
0x1800240b8  mov     rbp, [rsp+48h+arg_0]
0x1800240bd  test    cl, 2
0x1800240c0  jnz     short loc_1800240ED
0x1800240c2  mov     eax, ecx
0x1800240c4  xor     eax, edi
0x1800240c6  and     eax, 180h
0x1800240cb  xor     eax, ecx
0x1800240cd  mov     ecx, eax
0x1800240cf  xor     ecx, edi
0x1800240d1  and     ecx, 40h
0x1800240d4  xor     ecx, eax
0x1800240d6  mov     edx, ecx
0x1800240d8  xor     edx, edi
0x1800240da  and     edx, 1
0x1800240dd  xor     edx, ecx
0x1800240df  mov     ecx, edx
0x1800240e1  xor     ecx, edi
0x1800240e3  and     ecx, 800h
0x1800240e9  xor     ecx, edx
0x1800240eb  mov     [rbx], ecx
0x1800240ed  mov     rdi, [rsp+48h+var_18]
0x1800240f2  mov     rax, rbx
0x1800240f5  mov     rcx, [rsp+48h+var_20]
0x1800240fa  xor     rcx, rsp; StackCookie
0x1800240fd  call    __security_check_cookie
0x180024102  add     rsp, 38h
0x180024106  pop     r14
0x180024108  pop     rbx
0x180024109  retn
0x18002410a  mov     rax, rbx
0x18002410d  jmp     short loc_1800240F5
```
