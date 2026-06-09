# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(void)

- ea: `0x14000f964`
- end: `0x14000fad4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400128d4`
- `0x140013ae0`

## callees

- `0x140004d88`
- `0x140008f34`
- `0x14000f964`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ConfigRefresh__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(43467477, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
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
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ConfigRefresh__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ConfigRefresh__descriptor, 0, v4);
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
0x14000f964  mov     [rsp+arg_8], rbx
0x14000f969  mov     [rsp+arg_10], rbp
0x14000f96e  mov     [rsp+arg_0], rcx
0x14000f973  push    rsi
0x14000f974  push    rdi
0x14000f975  push    r15
0x14000f977  sub     rsp, 20h
0x14000f97b  mov     rsi, cs:Feature_ConfigRefresh__descriptor
0x14000f982  mov     rbx, rdx
0x14000f985  mov     qword ptr [rdx], 0
0x14000f98c  mov     eax, [rsi]
0x14000f98e  mov     [rdx], eax
0x14000f990  and     eax, 6
0x14000f993  cmp     al, 6
0x14000f995  jz      loc_14000FABD
0x14000f99b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000f9a0  mov     ebp, eax
0x14000f9a2  mov     dword ptr [rsp+38h+arg_0], 0
0x14000f9aa  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000f9b1  xor     edx, edx
0x14000f9b3  test    rax, rax
0x14000f9b6  jnz     short loc_14000F9C4
0x14000f9b8  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000f9bf  test    rax, rax
0x14000f9c2  jz      short loc_14000F9D5
0x14000f9c4  lea     r8, [rsp+38h+arg_0]
0x14000f9c9  mov     ecx, 29742D5h
0x14000f9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9d3  mov     edx, eax
0x14000f9d5  mov     r8d, edx
0x14000f9d8  mov     eax, edx
0x14000f9da  and     r8d, 0FFFFFF3Fh
0x14000f9e1  and     edx, 80h
0x14000f9e7  mov     ecx, r8d
0x14000f9ea  mov     r15d, 40h ; '@'
0x14000f9f0  and     ecx, 3
0x14000f9f3  and     eax, r15d
0x14000f9f6  shl     ecx, 2
0x14000f9f9  or      ecx, eax
0x14000f9fb  shl     ecx, 2
0x14000f9fe  or      ecx, edx
0x14000fa00  lea     edi, ds:0[rcx*8]
0x14000fa07  test    r8d, r8d
0x14000fa0a  jnz     short loc_14000FA11
0x14000fa0c  mov     eax, r15d
0x14000fa0f  jmp     short loc_14000FA1B
0x14000fa11  xor     eax, eax
0x14000fa13  cmp     r8d, 2
0x14000fa17  cmovz   eax, r15d
0x14000fa1b  or      edi, eax
0x14000fa1d  test    ebp, ebp
0x14000fa1f  jnz     short loc_14000FA25
0x14000fa21  mov     dword ptr [rsp+38h+arg_0], ebp
0x14000fa25  mov     eax, [rbx]
0x14000fa27  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000fa2c  mov     edx, eax
0x14000fa2e  mov     [rbx], eax
0x14000fa30  jz      short loc_14000FA5C
0x14000fa32  test    dl, 2
0x14000fa35  jnz     short loc_14000FA5C
0x14000fa37  xor     eax, edi
0x14000fa39  and     eax, 180h
0x14000fa3e  xor     eax, edx
0x14000fa40  mov     ecx, eax
0x14000fa42  xor     ecx, edi
0x14000fa44  and     ecx, r15d
0x14000fa47  xor     ecx, eax
0x14000fa49  or      ecx, 1
0x14000fa4c  mov     eax, ecx
0x14000fa4e  xor     eax, edi
0x14000fa50  and     eax, 800h
0x14000fa55  xor     eax, ecx
0x14000fa57  or      eax, 2
0x14000fa5a  mov     [rbx], eax
0x14000fa5c  mov     r8d, edx
0x14000fa5f  and     r8d, 4
0x14000fa63  jnz     short loc_14000FA78
0x14000fa65  mov     ecx, edi
0x14000fa67  xor     ecx, eax
0x14000fa69  and     ecx, 400h
0x14000fa6f  xor     ecx, eax
0x14000fa71  or      ecx, 4
0x14000fa74  mov     [rbx], ecx
0x14000fa76  jmp     short loc_14000FA7A
0x14000fa78  mov     ecx, eax
0x14000fa7a  mov     eax, edx
0x14000fa7c  lock cmpxchg [rsi], ecx
0x14000fa80  jnz     short loc_14000FA27
0x14000fa82  test    r8d, r8d
0x14000fa85  jnz     short loc_14000FA94
0x14000fa87  mov     r8d, ebp
0x14000fa8a  xor     edx, edx
0x14000fa8c  mov     rcx, rsi
0x14000fa8f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000fa94  test    byte ptr [rbx], 2
0x14000fa97  jnz     short loc_14000FABD
0x14000fa99  mov     eax, [rbx]
0x14000fa9b  xor     eax, edi
0x14000fa9d  and     eax, 180h
0x14000faa2  xor     eax, [rbx]
0x14000faa4  mov     ecx, eax
0x14000faa6  xor     ecx, edi
0x14000faa8  and     ecx, r15d
0x14000faab  xor     ecx, eax
0x14000faad  or      ecx, 1
0x14000fab0  mov     eax, ecx
0x14000fab2  xor     eax, edi
0x14000fab4  and     eax, 800h
0x14000fab9  xor     eax, ecx
0x14000fabb  mov     [rbx], eax
0x14000fabd  mov     rbp, [rsp+38h+arg_10]
0x14000fac2  mov     rax, rbx
0x14000fac5  mov     rbx, [rsp+38h+arg_8]
0x14000faca  add     rsp, 20h
0x14000face  pop     r15
0x14000fad0  pop     rdi
0x14000fad1  pop     rsi
0x14000fad2  retn
```
