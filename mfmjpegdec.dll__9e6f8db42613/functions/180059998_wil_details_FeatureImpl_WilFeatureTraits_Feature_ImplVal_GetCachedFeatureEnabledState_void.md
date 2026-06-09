# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)

- ea: `0x180059998`
- end: `0x180059af3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059f1c`

## callees

- `0x18003b30c`
- `0x18003d6a0`
- `0x18003d8e0`
- `0x180059998`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  unsigned int v6; // edx
  int *v7; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v9; // r8d
  int v10; // edi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  wil::details *v18; // [rsp+40h] [rbp+8h] BYREF

  v18 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ImplVal__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ImplVal__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x33B9B29,
                            v6,
                            (enum FEATURE_CHANGE_TIME)&v18,
                            v7);
    v9 = FeatureEnabledState & 0xFFFFFF3F;
    v10 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v11 = 0;
      if ( v9 == 2 )
        v11 = 64;
    }
    else
    {
      v11 = 64;
    }
    v12 = v11 | v10;
    v13 = *(_DWORD *)a2;
    do
    {
      v14 = (_DWORD)v18 == 0;
      v15 = v13;
      *(_DWORD *)a2 = v13;
      if ( !v14 && (v13 & 2) == 0 )
      {
        v13 = (v13
             ^ ((unsigned __int16)v13
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v13
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v13 ^ v12) & 0x180 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v13;
      }
      if ( (v15 & 4) != 0 )
      {
        v16 = v13;
      }
      else
      {
        v16 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v12) & 0x400 | 4;
        *(_DWORD *)a2 = v16;
      }
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ImplVal__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ImplVal__descriptor,
        3,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v12
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v12
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v12
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v12
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v12
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
0x180059998  mov     [rsp+arg_8], rbx
0x18005999d  mov     [rsp+arg_10], rbp
0x1800599a2  mov     [rsp+arg_0], rcx
0x1800599a7  push    rsi
0x1800599a8  push    rdi
0x1800599a9  push    r15
0x1800599ab  sub     rsp, 20h
0x1800599af  mov     rsi, cs:Feature_ImplVal__descriptor
0x1800599b6  mov     rbx, rdx
0x1800599b9  mov     qword ptr [rdx], 0
0x1800599c0  mov     eax, [rsi]
0x1800599c2  mov     [rdx], eax
0x1800599c4  and     eax, 6
0x1800599c7  cmp     al, 6
0x1800599c9  jz      loc_180059ADD
0x1800599cf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800599d4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800599d9  mov     dword ptr [rsp+38h+arg_0], 0
0x1800599e1  mov     ecx, 33B9B29h; this
0x1800599e6  mov     ebp, eax
0x1800599e8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800599ed  mov     r8d, eax
0x1800599f0  mov     ecx, eax
0x1800599f2  and     r8d, 0FFFFFF3Fh
0x1800599f9  and     eax, 80h
0x1800599fe  mov     edx, r8d
0x180059a01  mov     r15d, 40h ; '@'
0x180059a07  and     edx, 3
0x180059a0a  and     ecx, r15d
0x180059a0d  shl     edx, 2
0x180059a10  or      edx, ecx
0x180059a12  shl     edx, 2
0x180059a15  or      edx, eax
0x180059a17  lea     edi, ds:0[rdx*8]
0x180059a1e  test    r8d, r8d
0x180059a21  jnz     short loc_180059A28
0x180059a23  mov     eax, r15d
0x180059a26  jmp     short loc_180059A32
0x180059a28  xor     eax, eax
0x180059a2a  cmp     r8d, 2
0x180059a2e  cmovz   eax, r15d
0x180059a32  or      edi, eax
0x180059a34  mov     eax, [rbx]
0x180059a36  cmp     dword ptr [rsp+38h+arg_0], 0
0x180059a3b  mov     edx, eax
0x180059a3d  mov     [rbx], eax
0x180059a3f  jz      short loc_180059A6F
0x180059a41  test    dl, 2
0x180059a44  jnz     short loc_180059A6F
0x180059a46  mov     eax, edi
0x180059a48  xor     eax, edx
0x180059a4a  and     eax, 180h
0x180059a4f  xor     eax, edx
0x180059a51  mov     ecx, eax
0x180059a53  xor     ecx, edi
0x180059a55  and     ecx, r15d
0x180059a58  xor     ecx, eax
0x180059a5a  or      ecx, 1
0x180059a5d  mov     eax, ecx
0x180059a5f  xor     eax, edi
0x180059a61  and     eax, 800h
0x180059a66  xor     eax, ecx
0x180059a68  or      eax, 2
0x180059a6b  mov     [rbx], eax
0x180059a6d  jmp     short loc_180059A71
0x180059a6f  mov     eax, edx
0x180059a71  mov     r8d, edx
0x180059a74  and     r8d, 4
0x180059a78  jnz     short loc_180059A8D
0x180059a7a  mov     ecx, edi
0x180059a7c  xor     ecx, eax
0x180059a7e  and     ecx, 400h
0x180059a84  xor     ecx, eax
0x180059a86  or      ecx, 4
0x180059a89  mov     [rbx], ecx
0x180059a8b  jmp     short loc_180059A8F
0x180059a8d  mov     ecx, eax
0x180059a8f  mov     eax, edx
0x180059a91  lock cmpxchg [rsi], ecx
0x180059a95  jnz     short loc_180059A36
0x180059a97  test    r8d, r8d
0x180059a9a  jnz     short loc_180059AB4
0x180059a9c  mov     r9d, ebp
0x180059a9f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059aa6  mov     r8d, 3
0x180059aac  mov     rdx, rsi
0x180059aaf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180059ab4  test    byte ptr [rbx], 2
0x180059ab7  jnz     short loc_180059ADD
0x180059ab9  mov     eax, [rbx]
0x180059abb  xor     eax, edi
0x180059abd  and     eax, 180h
0x180059ac2  xor     eax, [rbx]
0x180059ac4  mov     ecx, eax
0x180059ac6  xor     ecx, edi
0x180059ac8  and     ecx, r15d
0x180059acb  xor     ecx, eax
0x180059acd  or      ecx, 1
0x180059ad0  mov     eax, ecx
0x180059ad2  xor     eax, edi
0x180059ad4  and     eax, 800h
0x180059ad9  xor     eax, ecx
0x180059adb  mov     [rbx], eax
0x180059add  mov     rbp, [rsp+38h+arg_10]
0x180059ae2  mov     rax, rbx
0x180059ae5  mov     rbx, [rsp+38h+arg_8]
0x180059aea  add     rsp, 20h
0x180059aee  pop     r15
0x180059af0  pop     rdi
0x180059af1  pop     rsi
0x180059af2  retn
```
