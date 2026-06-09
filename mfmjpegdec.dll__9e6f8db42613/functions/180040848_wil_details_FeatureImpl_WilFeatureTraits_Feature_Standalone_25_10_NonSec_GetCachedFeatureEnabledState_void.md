# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180040848`
- end: `0x1800409a3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800409ac`

## callees

- `0x18003b30c`
- `0x18003d6a0`
- `0x18003d8e0`
- `0x180040848`

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
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
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
0x180040848  mov     [rsp+arg_8], rbx
0x18004084d  mov     [rsp+arg_10], rbp
0x180040852  mov     [rsp+arg_0], rcx
0x180040857  push    rsi
0x180040858  push    rdi
0x180040859  push    r15
0x18004085b  sub     rsp, 20h
0x18004085f  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180040866  mov     rbx, rdx
0x180040869  mov     qword ptr [rdx], 0
0x180040870  mov     eax, [rsi]
0x180040872  mov     [rdx], eax
0x180040874  and     eax, 6
0x180040877  cmp     al, 6
0x180040879  jz      loc_18004098D
0x18004087f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180040884  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180040889  mov     dword ptr [rsp+38h+arg_0], 0
0x180040891  mov     ecx, 2AF34F8h; this
0x180040896  mov     ebp, eax
0x180040898  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18004089d  mov     r8d, eax
0x1800408a0  mov     ecx, eax
0x1800408a2  and     r8d, 0FFFFFF3Fh
0x1800408a9  and     eax, 80h
0x1800408ae  mov     edx, r8d
0x1800408b1  mov     r15d, 40h ; '@'
0x1800408b7  and     edx, 3
0x1800408ba  and     ecx, r15d
0x1800408bd  shl     edx, 2
0x1800408c0  or      edx, ecx
0x1800408c2  shl     edx, 2
0x1800408c5  or      edx, eax
0x1800408c7  lea     edi, ds:0[rdx*8]
0x1800408ce  test    r8d, r8d
0x1800408d1  jnz     short loc_1800408D8
0x1800408d3  mov     eax, r15d
0x1800408d6  jmp     short loc_1800408E2
0x1800408d8  xor     eax, eax
0x1800408da  cmp     r8d, 2
0x1800408de  cmovz   eax, r15d
0x1800408e2  or      edi, eax
0x1800408e4  mov     eax, [rbx]
0x1800408e6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800408eb  mov     edx, eax
0x1800408ed  mov     [rbx], eax
0x1800408ef  jz      short loc_18004091F
0x1800408f1  test    dl, 2
0x1800408f4  jnz     short loc_18004091F
0x1800408f6  mov     eax, edi
0x1800408f8  xor     eax, edx
0x1800408fa  and     eax, 180h
0x1800408ff  xor     eax, edx
0x180040901  mov     ecx, eax
0x180040903  xor     ecx, edi
0x180040905  and     ecx, r15d
0x180040908  xor     ecx, eax
0x18004090a  or      ecx, 1
0x18004090d  mov     eax, ecx
0x18004090f  xor     eax, edi
0x180040911  and     eax, 800h
0x180040916  xor     eax, ecx
0x180040918  or      eax, 2
0x18004091b  mov     [rbx], eax
0x18004091d  jmp     short loc_180040921
0x18004091f  mov     eax, edx
0x180040921  mov     r8d, edx
0x180040924  and     r8d, 4
0x180040928  jnz     short loc_18004093D
0x18004092a  mov     ecx, edi
0x18004092c  xor     ecx, eax
0x18004092e  and     ecx, 400h
0x180040934  xor     ecx, eax
0x180040936  or      ecx, 4
0x180040939  mov     [rbx], ecx
0x18004093b  jmp     short loc_18004093F
0x18004093d  mov     ecx, eax
0x18004093f  mov     eax, edx
0x180040941  lock cmpxchg [rsi], ecx
0x180040945  jnz     short loc_1800408E6
0x180040947  test    r8d, r8d
0x18004094a  jnz     short loc_180040964
0x18004094c  mov     r9d, ebp
0x18004094f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180040956  mov     r8d, 3
0x18004095c  mov     rdx, rsi
0x18004095f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180040964  test    byte ptr [rbx], 2
0x180040967  jnz     short loc_18004098D
0x180040969  mov     eax, [rbx]
0x18004096b  xor     eax, edi
0x18004096d  and     eax, 180h
0x180040972  xor     eax, [rbx]
0x180040974  mov     ecx, eax
0x180040976  xor     ecx, edi
0x180040978  and     ecx, r15d
0x18004097b  xor     ecx, eax
0x18004097d  or      ecx, 1
0x180040980  mov     eax, ecx
0x180040982  xor     eax, edi
0x180040984  and     eax, 800h
0x180040989  xor     eax, ecx
0x18004098b  mov     [rbx], eax
0x18004098d  mov     rbp, [rsp+38h+arg_10]
0x180040992  mov     rax, rbx
0x180040995  mov     rbx, [rsp+38h+arg_8]
0x18004099a  add     rsp, 20h
0x18004099e  pop     r15
0x1800409a0  pop     rdi
0x1800409a1  pop     rsi
0x1800409a2  retn
```
