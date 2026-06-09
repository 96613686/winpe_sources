# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions>::GetCachedFeatureEnabledState(void)

- ea: `0x180019d00`
- end: `0x180019e59`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019e60`

## callees

- `0x1800110e8`
- `0x180014608`
- `0x180014da4`
- `0x180019d00`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoexPassesStructuredExceptions>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_NegoexPassesStructuredExceptions__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NegoexPassesStructuredExceptions__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x1BD9FE6,
                            0,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    if ( !v5 )
      LODWORD(v17) = 0;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v11
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v11
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v11 ^ v12) & 0x180 ^ (v11 ^ v12 ^ (v11 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_NegoexPassesStructuredExceptions__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_NegoexPassesStructuredExceptions__descriptor,
        v14 & 4,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x180019d00  mov     [rsp+arg_8], rbx
0x180019d05  mov     [rsp+arg_10], rbp
0x180019d0a  mov     [rsp+arg_0], rcx
0x180019d0f  push    rsi
0x180019d10  push    rdi
0x180019d11  push    r15
0x180019d13  sub     rsp, 20h
0x180019d17  mov     rsi, cs:Feature_NegoexPassesStructuredExceptions__descriptor
0x180019d1e  mov     rbx, rdx
0x180019d21  mov     qword ptr [rdx], 0
0x180019d28  mov     eax, [rsi]
0x180019d2a  mov     [rdx], eax
0x180019d2c  and     eax, 6
0x180019d2f  cmp     al, 6
0x180019d31  jz      loc_180019E43
0x180019d37  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180019d3c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180019d41  mov     dword ptr [rsp+38h+arg_0], 0
0x180019d49  xor     edx, edx; unsigned int
0x180019d4b  mov     ecx, 1BD9FE6h; this
0x180019d50  mov     ebp, eax
0x180019d52  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180019d57  mov     r8d, eax
0x180019d5a  mov     ecx, eax
0x180019d5c  and     r8d, 0FFFFFF3Fh
0x180019d63  and     eax, 80h
0x180019d68  mov     edx, r8d
0x180019d6b  mov     r15d, 40h ; '@'
0x180019d71  and     edx, 3
0x180019d74  and     ecx, r15d
0x180019d77  shl     edx, 2
0x180019d7a  or      edx, ecx
0x180019d7c  shl     edx, 2
0x180019d7f  or      edx, eax
0x180019d81  lea     edi, ds:0[rdx*8]
0x180019d88  test    r8d, r8d
0x180019d8b  jnz     short loc_180019D92
0x180019d8d  mov     eax, r15d
0x180019d90  jmp     short loc_180019D9C
0x180019d92  xor     eax, eax
0x180019d94  cmp     r8d, 2
0x180019d98  cmovz   eax, r15d
0x180019d9c  or      edi, eax
0x180019d9e  test    ebp, ebp
0x180019da0  jnz     short loc_180019DA6
0x180019da2  mov     dword ptr [rsp+38h+arg_0], ebp
0x180019da6  mov     eax, [rbx]
0x180019da8  cmp     dword ptr [rsp+38h+arg_0], 0
0x180019dad  mov     edx, eax
0x180019daf  mov     [rbx], eax
0x180019db1  jz      short loc_180019DDD
0x180019db3  test    dl, 2
0x180019db6  jnz     short loc_180019DDD
0x180019db8  xor     eax, edi
0x180019dba  and     eax, 180h
0x180019dbf  xor     eax, edx
0x180019dc1  mov     ecx, eax
0x180019dc3  xor     ecx, edi
0x180019dc5  and     ecx, r15d
0x180019dc8  xor     ecx, eax
0x180019dca  or      ecx, 1
0x180019dcd  mov     eax, ecx
0x180019dcf  xor     eax, edi
0x180019dd1  and     eax, 800h
0x180019dd6  xor     eax, ecx
0x180019dd8  or      eax, 2
0x180019ddb  mov     [rbx], eax
0x180019ddd  mov     r8d, edx
0x180019de0  and     r8d, 4
0x180019de4  jnz     short loc_180019DF9
0x180019de6  mov     ecx, edi
0x180019de8  xor     ecx, eax
0x180019dea  and     ecx, 400h
0x180019df0  xor     ecx, eax
0x180019df2  or      ecx, 4
0x180019df5  mov     [rbx], ecx
0x180019df7  jmp     short loc_180019DFB
0x180019df9  mov     ecx, eax
0x180019dfb  mov     eax, edx
0x180019dfd  lock cmpxchg [rsi], ecx
0x180019e01  jnz     short loc_180019DA8
0x180019e03  test    r8d, r8d
0x180019e06  jnz     short loc_180019E1A
0x180019e08  mov     r9d, ebp
0x180019e0b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180019e12  mov     rdx, rsi
0x180019e15  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180019e1a  test    byte ptr [rbx], 2
0x180019e1d  jnz     short loc_180019E43
0x180019e1f  mov     eax, [rbx]
0x180019e21  xor     eax, edi
0x180019e23  and     eax, 180h
0x180019e28  xor     eax, [rbx]
0x180019e2a  mov     ecx, eax
0x180019e2c  xor     ecx, edi
0x180019e2e  and     ecx, r15d
0x180019e31  xor     ecx, eax
0x180019e33  or      ecx, 1
0x180019e36  mov     eax, ecx
0x180019e38  xor     eax, edi
0x180019e3a  and     eax, 800h
0x180019e3f  xor     eax, ecx
0x180019e41  mov     [rbx], eax
0x180019e43  mov     rbp, [rsp+38h+arg_10]
0x180019e48  mov     rax, rbx
0x180019e4b  mov     rbx, [rsp+38h+arg_8]
0x180019e50  add     rsp, 20h
0x180019e54  pop     r15
0x180019e56  pop     rdi
0x180019e57  pop     rsi
0x180019e58  retn
```
