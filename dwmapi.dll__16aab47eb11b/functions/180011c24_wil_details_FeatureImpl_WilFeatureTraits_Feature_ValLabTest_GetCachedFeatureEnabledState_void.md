# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180011c24`
- end: `0x180011d7f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011e50`

## callees

- `0x18000eb58`
- `0x18001011c`
- `0x180011c24`
- `0x180012420`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667CA2,
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
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x180011c24  mov     [rsp+arg_8], rbx
0x180011c29  mov     [rsp+arg_10], rbp
0x180011c2e  mov     [rsp+arg_0], rcx
0x180011c33  push    rsi
0x180011c34  push    rdi
0x180011c35  push    r15
0x180011c37  sub     rsp, 20h
0x180011c3b  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180011c42  mov     rbx, rdx
0x180011c45  mov     qword ptr [rdx], 0
0x180011c4c  mov     eax, [rsi]
0x180011c4e  mov     [rdx], eax
0x180011c50  and     eax, 6
0x180011c53  cmp     al, 6
0x180011c55  jz      loc_180011D69
0x180011c5b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011c60  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180011c65  mov     dword ptr [rsp+38h+arg_0], 0
0x180011c6d  mov     ecx, 3667CA2h; this
0x180011c72  mov     ebp, eax
0x180011c74  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180011c79  mov     r8d, eax
0x180011c7c  mov     ecx, eax
0x180011c7e  and     r8d, 0FFFFFF3Fh
0x180011c85  and     eax, 80h
0x180011c8a  mov     edx, r8d
0x180011c8d  mov     r15d, 40h ; '@'
0x180011c93  and     edx, 3
0x180011c96  and     ecx, r15d
0x180011c99  shl     edx, 2
0x180011c9c  or      edx, ecx
0x180011c9e  shl     edx, 2
0x180011ca1  or      edx, eax
0x180011ca3  lea     edi, ds:0[rdx*8]
0x180011caa  test    r8d, r8d
0x180011cad  jnz     short loc_180011CB4
0x180011caf  mov     eax, r15d
0x180011cb2  jmp     short loc_180011CBE
0x180011cb4  xor     eax, eax
0x180011cb6  cmp     r8d, 2
0x180011cba  cmovz   eax, r15d
0x180011cbe  or      edi, eax
0x180011cc0  mov     eax, [rbx]
0x180011cc2  cmp     dword ptr [rsp+38h+arg_0], 0
0x180011cc7  mov     edx, eax
0x180011cc9  mov     [rbx], eax
0x180011ccb  jz      short loc_180011CFB
0x180011ccd  test    dl, 2
0x180011cd0  jnz     short loc_180011CFB
0x180011cd2  mov     eax, edi
0x180011cd4  xor     eax, edx
0x180011cd6  and     eax, 180h
0x180011cdb  xor     eax, edx
0x180011cdd  mov     ecx, eax
0x180011cdf  xor     ecx, edi
0x180011ce1  and     ecx, r15d
0x180011ce4  xor     ecx, eax
0x180011ce6  or      ecx, 1
0x180011ce9  mov     eax, ecx
0x180011ceb  xor     eax, edi
0x180011ced  and     eax, 800h
0x180011cf2  xor     eax, ecx
0x180011cf4  or      eax, 2
0x180011cf7  mov     [rbx], eax
0x180011cf9  jmp     short loc_180011CFD
0x180011cfb  mov     eax, edx
0x180011cfd  mov     r8d, edx
0x180011d00  and     r8d, 4
0x180011d04  jnz     short loc_180011D19
0x180011d06  mov     ecx, edi
0x180011d08  xor     ecx, eax
0x180011d0a  and     ecx, 400h
0x180011d10  xor     ecx, eax
0x180011d12  or      ecx, 4
0x180011d15  mov     [rbx], ecx
0x180011d17  jmp     short loc_180011D1B
0x180011d19  mov     ecx, eax
0x180011d1b  mov     eax, edx
0x180011d1d  lock cmpxchg [rsi], ecx
0x180011d21  jnz     short loc_180011CC2
0x180011d23  test    r8d, r8d
0x180011d26  jnz     short loc_180011D40
0x180011d28  mov     r9d, ebp
0x180011d2b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011d32  mov     r8d, 3
0x180011d38  mov     rdx, rsi
0x180011d3b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180011d40  test    byte ptr [rbx], 2
0x180011d43  jnz     short loc_180011D69
0x180011d45  mov     eax, [rbx]
0x180011d47  xor     eax, edi
0x180011d49  and     eax, 180h
0x180011d4e  xor     eax, [rbx]
0x180011d50  mov     ecx, eax
0x180011d52  xor     ecx, edi
0x180011d54  and     ecx, r15d
0x180011d57  xor     ecx, eax
0x180011d59  or      ecx, 1
0x180011d5c  mov     eax, ecx
0x180011d5e  xor     eax, edi
0x180011d60  and     eax, 800h
0x180011d65  xor     eax, ecx
0x180011d67  mov     [rbx], eax
0x180011d69  mov     rbp, [rsp+38h+arg_10]
0x180011d6e  mov     rax, rbx
0x180011d71  mov     rbx, [rsp+38h+arg_8]
0x180011d76  add     rsp, 20h
0x180011d7a  pop     r15
0x180011d7c  pop     rdi
0x180011d7d  pop     rsi
0x180011d7e  retn
```
