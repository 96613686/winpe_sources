# wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(void)

- ea: `0x14000fadc`
- end: `0x14000fc4c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000fff0`

## callees

- `0x140004d88`
- `0x140008f34`
- `0x14000fadc`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57312060, 0, &v14);
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
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor,
        0,
        v4);
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
0x14000fadc  mov     [rsp+arg_8], rbx
0x14000fae1  mov     [rsp+arg_10], rbp
0x14000fae6  mov     [rsp+arg_0], rcx
0x14000faeb  push    rsi
0x14000faec  push    rdi
0x14000faed  push    r15
0x14000faef  sub     rsp, 20h
0x14000faf3  mov     rsi, cs:Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor
0x14000fafa  mov     rbx, rdx
0x14000fafd  mov     qword ptr [rdx], 0
0x14000fb04  mov     eax, [rsi]
0x14000fb06  mov     [rdx], eax
0x14000fb08  and     eax, 6
0x14000fb0b  cmp     al, 6
0x14000fb0d  jz      loc_14000FC35
0x14000fb13  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000fb18  mov     ebp, eax
0x14000fb1a  mov     dword ptr [rsp+38h+arg_0], 0
0x14000fb22  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000fb29  xor     edx, edx
0x14000fb2b  test    rax, rax
0x14000fb2e  jnz     short loc_14000FB3C
0x14000fb30  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000fb37  test    rax, rax
0x14000fb3a  jz      short loc_14000FB4D
0x14000fb3c  lea     r8, [rsp+38h+arg_0]
0x14000fb41  mov     ecx, 36A833Ch
0x14000fb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb4b  mov     edx, eax
0x14000fb4d  mov     r8d, edx
0x14000fb50  mov     eax, edx
0x14000fb52  and     r8d, 0FFFFFF3Fh
0x14000fb59  and     edx, 80h
0x14000fb5f  mov     ecx, r8d
0x14000fb62  mov     r15d, 40h ; '@'
0x14000fb68  and     ecx, 3
0x14000fb6b  and     eax, r15d
0x14000fb6e  shl     ecx, 2
0x14000fb71  or      ecx, eax
0x14000fb73  shl     ecx, 2
0x14000fb76  or      ecx, edx
0x14000fb78  lea     edi, ds:0[rcx*8]
0x14000fb7f  test    r8d, r8d
0x14000fb82  jnz     short loc_14000FB89
0x14000fb84  mov     eax, r15d
0x14000fb87  jmp     short loc_14000FB93
0x14000fb89  xor     eax, eax
0x14000fb8b  cmp     r8d, 2
0x14000fb8f  cmovz   eax, r15d
0x14000fb93  or      edi, eax
0x14000fb95  test    ebp, ebp
0x14000fb97  jnz     short loc_14000FB9D
0x14000fb99  mov     dword ptr [rsp+38h+arg_0], ebp
0x14000fb9d  mov     eax, [rbx]
0x14000fb9f  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000fba4  mov     edx, eax
0x14000fba6  mov     [rbx], eax
0x14000fba8  jz      short loc_14000FBD4
0x14000fbaa  test    dl, 2
0x14000fbad  jnz     short loc_14000FBD4
0x14000fbaf  xor     eax, edi
0x14000fbb1  and     eax, 180h
0x14000fbb6  xor     eax, edx
0x14000fbb8  mov     ecx, eax
0x14000fbba  xor     ecx, edi
0x14000fbbc  and     ecx, r15d
0x14000fbbf  xor     ecx, eax
0x14000fbc1  or      ecx, 1
0x14000fbc4  mov     eax, ecx
0x14000fbc6  xor     eax, edi
0x14000fbc8  and     eax, 800h
0x14000fbcd  xor     eax, ecx
0x14000fbcf  or      eax, 2
0x14000fbd2  mov     [rbx], eax
0x14000fbd4  mov     r8d, edx
0x14000fbd7  and     r8d, 4
0x14000fbdb  jnz     short loc_14000FBF0
0x14000fbdd  mov     ecx, edi
0x14000fbdf  xor     ecx, eax
0x14000fbe1  and     ecx, 400h
0x14000fbe7  xor     ecx, eax
0x14000fbe9  or      ecx, 4
0x14000fbec  mov     [rbx], ecx
0x14000fbee  jmp     short loc_14000FBF2
0x14000fbf0  mov     ecx, eax
0x14000fbf2  mov     eax, edx
0x14000fbf4  lock cmpxchg [rsi], ecx
0x14000fbf8  jnz     short loc_14000FB9F
0x14000fbfa  test    r8d, r8d
0x14000fbfd  jnz     short loc_14000FC0C
0x14000fbff  mov     r8d, ebp
0x14000fc02  xor     edx, edx
0x14000fc04  mov     rcx, rsi
0x14000fc07  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000fc0c  test    byte ptr [rbx], 2
0x14000fc0f  jnz     short loc_14000FC35
0x14000fc11  mov     eax, [rbx]
0x14000fc13  xor     eax, edi
0x14000fc15  and     eax, 180h
0x14000fc1a  xor     eax, [rbx]
0x14000fc1c  mov     ecx, eax
0x14000fc1e  xor     ecx, edi
0x14000fc20  and     ecx, r15d
0x14000fc23  xor     ecx, eax
0x14000fc25  or      ecx, 1
0x14000fc28  mov     eax, ecx
0x14000fc2a  xor     eax, edi
0x14000fc2c  and     eax, 800h
0x14000fc31  xor     eax, ecx
0x14000fc33  mov     [rbx], eax
0x14000fc35  mov     rbp, [rsp+38h+arg_10]
0x14000fc3a  mov     rax, rbx
0x14000fc3d  mov     rbx, [rsp+38h+arg_8]
0x14000fc42  add     rsp, 20h
0x14000fc46  pop     r15
0x14000fc48  pop     rdi
0x14000fc49  pop     rsi
0x14000fc4a  retn
```
