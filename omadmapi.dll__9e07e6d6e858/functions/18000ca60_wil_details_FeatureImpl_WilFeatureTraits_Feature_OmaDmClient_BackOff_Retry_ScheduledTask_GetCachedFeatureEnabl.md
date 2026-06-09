# wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ca60`
- end: `0x18000cbd0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b0d0`
- `0x18001e844`

## callees

- `0x18000bdd8`
- `0x18000ca60`
- `0x180012fb4`
- `0x180024010`

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
0x18000ca60  mov     [rsp+arg_8], rbx
0x18000ca65  mov     [rsp+arg_10], rbp
0x18000ca6a  mov     [rsp+arg_0], rcx
0x18000ca6f  push    rsi
0x18000ca70  push    rdi
0x18000ca71  push    r15
0x18000ca73  sub     rsp, 20h
0x18000ca77  mov     rsi, cs:Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor
0x18000ca7e  mov     rbx, rdx
0x18000ca81  mov     qword ptr [rdx], 0
0x18000ca88  mov     eax, [rsi]
0x18000ca8a  mov     [rdx], eax
0x18000ca8c  and     eax, 6
0x18000ca8f  cmp     al, 6
0x18000ca91  jz      loc_18000CBB9
0x18000ca97  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ca9c  mov     ebp, eax
0x18000ca9e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000caa6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000caad  xor     edx, edx
0x18000caaf  test    rax, rax
0x18000cab2  jnz     short loc_18000CAC0
0x18000cab4  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000cabb  test    rax, rax
0x18000cabe  jz      short loc_18000CAD1
0x18000cac0  lea     r8, [rsp+38h+arg_0]
0x18000cac5  mov     ecx, 36A833Ch
0x18000caca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cacf  mov     edx, eax
0x18000cad1  mov     r8d, edx
0x18000cad4  mov     eax, edx
0x18000cad6  and     r8d, 0FFFFFF3Fh
0x18000cadd  and     edx, 80h
0x18000cae3  mov     ecx, r8d
0x18000cae6  mov     r15d, 40h ; '@'
0x18000caec  and     ecx, 3
0x18000caef  and     eax, r15d
0x18000caf2  shl     ecx, 2
0x18000caf5  or      ecx, eax
0x18000caf7  shl     ecx, 2
0x18000cafa  or      ecx, edx
0x18000cafc  lea     edi, ds:0[rcx*8]
0x18000cb03  test    r8d, r8d
0x18000cb06  jnz     short loc_18000CB0D
0x18000cb08  mov     eax, r15d
0x18000cb0b  jmp     short loc_18000CB17
0x18000cb0d  xor     eax, eax
0x18000cb0f  cmp     r8d, 2
0x18000cb13  cmovz   eax, r15d
0x18000cb17  or      edi, eax
0x18000cb19  test    ebp, ebp
0x18000cb1b  jnz     short loc_18000CB21
0x18000cb1d  mov     dword ptr [rsp+38h+arg_0], ebp
0x18000cb21  mov     eax, [rbx]
0x18000cb23  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000cb28  mov     edx, eax
0x18000cb2a  mov     [rbx], eax
0x18000cb2c  jz      short loc_18000CB58
0x18000cb2e  test    dl, 2
0x18000cb31  jnz     short loc_18000CB58
0x18000cb33  xor     eax, edi
0x18000cb35  and     eax, 180h
0x18000cb3a  xor     eax, edx
0x18000cb3c  mov     ecx, eax
0x18000cb3e  xor     ecx, edi
0x18000cb40  and     ecx, r15d
0x18000cb43  xor     ecx, eax
0x18000cb45  or      ecx, 1
0x18000cb48  mov     eax, ecx
0x18000cb4a  xor     eax, edi
0x18000cb4c  and     eax, 800h
0x18000cb51  xor     eax, ecx
0x18000cb53  or      eax, 2
0x18000cb56  mov     [rbx], eax
0x18000cb58  mov     r8d, edx
0x18000cb5b  and     r8d, 4
0x18000cb5f  jnz     short loc_18000CB74
0x18000cb61  mov     ecx, edi
0x18000cb63  xor     ecx, eax
0x18000cb65  and     ecx, 400h
0x18000cb6b  xor     ecx, eax
0x18000cb6d  or      ecx, 4
0x18000cb70  mov     [rbx], ecx
0x18000cb72  jmp     short loc_18000CB76
0x18000cb74  mov     ecx, eax
0x18000cb76  mov     eax, edx
0x18000cb78  lock cmpxchg [rsi], ecx
0x18000cb7c  jnz     short loc_18000CB23
0x18000cb7e  test    r8d, r8d
0x18000cb81  jnz     short loc_18000CB90
0x18000cb83  mov     r8d, ebp
0x18000cb86  xor     edx, edx
0x18000cb88  mov     rcx, rsi
0x18000cb8b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000cb90  test    byte ptr [rbx], 2
0x18000cb93  jnz     short loc_18000CBB9
0x18000cb95  mov     eax, [rbx]
0x18000cb97  xor     eax, edi
0x18000cb99  and     eax, 180h
0x18000cb9e  xor     eax, [rbx]
0x18000cba0  mov     ecx, eax
0x18000cba2  xor     ecx, edi
0x18000cba4  and     ecx, r15d
0x18000cba7  xor     ecx, eax
0x18000cba9  or      ecx, 1
0x18000cbac  mov     eax, ecx
0x18000cbae  xor     eax, edi
0x18000cbb0  and     eax, 800h
0x18000cbb5  xor     eax, ecx
0x18000cbb7  mov     [rbx], eax
0x18000cbb9  mov     rbp, [rsp+38h+arg_10]
0x18000cbbe  mov     rax, rbx
0x18000cbc1  mov     rbx, [rsp+38h+arg_8]
0x18000cbc6  add     rsp, 20h
0x18000cbca  pop     r15
0x18000cbcc  pop     rdi
0x18000cbcd  pop     rsi
0x18000cbce  retn
```
