# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800119d8`
- end: `0x180011b33`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
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
- `0x1800119d8`
- `0x180012420`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34F8,
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
      v13 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x1800119d8  mov     [rsp+arg_8], rbx
0x1800119dd  mov     [rsp+arg_10], rbp
0x1800119e2  mov     [rsp+arg_0], rcx
0x1800119e7  push    rsi
0x1800119e8  push    rdi
0x1800119e9  push    r15
0x1800119eb  sub     rsp, 20h
0x1800119ef  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800119f6  mov     rbx, rdx
0x1800119f9  mov     qword ptr [rdx], 0
0x180011a00  mov     eax, [rsi]
0x180011a02  mov     [rdx], eax
0x180011a04  and     eax, 6
0x180011a07  cmp     al, 6
0x180011a09  jz      loc_180011B1D
0x180011a0f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011a14  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180011a19  mov     dword ptr [rsp+38h+arg_0], 0
0x180011a21  mov     ecx, 2AF34F8h; this
0x180011a26  mov     ebp, eax
0x180011a28  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180011a2d  mov     r8d, eax
0x180011a30  mov     ecx, eax
0x180011a32  and     r8d, 0FFFFFF3Fh
0x180011a39  and     eax, 80h
0x180011a3e  mov     edx, r8d
0x180011a41  mov     r15d, 40h ; '@'
0x180011a47  and     edx, 3
0x180011a4a  and     ecx, r15d
0x180011a4d  shl     edx, 2
0x180011a50  or      edx, ecx
0x180011a52  shl     edx, 2
0x180011a55  or      edx, eax
0x180011a57  lea     edi, ds:0[rdx*8]
0x180011a5e  test    r8d, r8d
0x180011a61  jnz     short loc_180011A68
0x180011a63  mov     eax, r15d
0x180011a66  jmp     short loc_180011A72
0x180011a68  xor     eax, eax
0x180011a6a  cmp     r8d, 2
0x180011a6e  cmovz   eax, r15d
0x180011a72  or      edi, eax
0x180011a74  mov     eax, [rbx]
0x180011a76  cmp     dword ptr [rsp+38h+arg_0], 0
0x180011a7b  mov     edx, eax
0x180011a7d  mov     [rbx], eax
0x180011a7f  jz      short loc_180011AAF
0x180011a81  test    dl, 2
0x180011a84  jnz     short loc_180011AAF
0x180011a86  mov     eax, edi
0x180011a88  xor     eax, edx
0x180011a8a  and     eax, 180h
0x180011a8f  xor     eax, edx
0x180011a91  mov     ecx, eax
0x180011a93  xor     ecx, edi
0x180011a95  and     ecx, r15d
0x180011a98  xor     ecx, eax
0x180011a9a  or      ecx, 1
0x180011a9d  mov     eax, ecx
0x180011a9f  xor     eax, edi
0x180011aa1  and     eax, 800h
0x180011aa6  xor     eax, ecx
0x180011aa8  or      eax, 2
0x180011aab  mov     [rbx], eax
0x180011aad  jmp     short loc_180011AB1
0x180011aaf  mov     eax, edx
0x180011ab1  mov     r8d, edx
0x180011ab4  and     r8d, 4
0x180011ab8  jnz     short loc_180011ACD
0x180011aba  mov     ecx, edi
0x180011abc  xor     ecx, eax
0x180011abe  and     ecx, 400h
0x180011ac4  xor     ecx, eax
0x180011ac6  or      ecx, 4
0x180011ac9  mov     [rbx], ecx
0x180011acb  jmp     short loc_180011ACF
0x180011acd  mov     ecx, eax
0x180011acf  mov     eax, edx
0x180011ad1  lock cmpxchg [rsi], ecx
0x180011ad5  jnz     short loc_180011A76
0x180011ad7  test    r8d, r8d
0x180011ada  jnz     short loc_180011AF4
0x180011adc  mov     r9d, ebp
0x180011adf  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011ae6  mov     r8d, 3
0x180011aec  mov     rdx, rsi
0x180011aef  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180011af4  test    byte ptr [rbx], 2
0x180011af7  jnz     short loc_180011B1D
0x180011af9  mov     eax, [rbx]
0x180011afb  xor     eax, edi
0x180011afd  and     eax, 180h
0x180011b02  xor     eax, [rbx]
0x180011b04  mov     ecx, eax
0x180011b06  xor     ecx, edi
0x180011b08  and     ecx, r15d
0x180011b0b  xor     ecx, eax
0x180011b0d  or      ecx, 1
0x180011b10  mov     eax, ecx
0x180011b12  xor     eax, edi
0x180011b14  and     eax, 800h
0x180011b19  xor     eax, ecx
0x180011b1b  mov     [rbx], eax
0x180011b1d  mov     rbp, [rsp+38h+arg_10]
0x180011b22  mov     rax, rbx
0x180011b25  mov     rbx, [rsp+38h+arg_8]
0x180011b2a  add     rsp, 20h
0x180011b2e  pop     r15
0x180011b30  pop     rdi
0x180011b31  pop     rsi
0x180011b32  retn
```
