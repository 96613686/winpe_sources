# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ee44`
- end: `0x18000efb1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8d4`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000ee44`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599553, 3, &v14);
    }
    else
    {
      v6 = 0;
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
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor,
        3,
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
0x18000ee44  mov     [rsp+arg_8], rbx
0x18000ee49  mov     [rsp+arg_10], rbp
0x18000ee4e  mov     [rsp+arg_0], rcx
0x18000ee53  push    rsi
0x18000ee54  push    rdi
0x18000ee55  push    r15
0x18000ee57  sub     rsp, 20h
0x18000ee5b  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000ee62  mov     rbx, rdx
0x18000ee65  mov     qword ptr [rdx], 0
0x18000ee6c  mov     eax, [rsi]
0x18000ee6e  mov     [rdx], eax
0x18000ee70  and     eax, 6
0x18000ee73  cmp     al, 6
0x18000ee75  jz      loc_18000EF9B
0x18000ee7b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ee80  mov     ebp, eax
0x18000ee82  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ee8a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ee91  test    rax, rax
0x18000ee94  jz      short loc_18000EEAE
0x18000ee96  lea     r8, [rsp+38h+arg_0]
0x18000ee9b  mov     edx, 3
0x18000eea0  mov     ecx, 37E2881h
0x18000eea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeaa  mov     edx, eax
0x18000eeac  jmp     short loc_18000EEBC
0x18000eeae  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000eeb5  test    rax, rax
0x18000eeb8  jnz     short loc_18000EE96
0x18000eeba  xor     edx, edx
0x18000eebc  mov     r8d, edx
0x18000eebf  mov     eax, edx
0x18000eec1  and     r8d, 0FFFFFF3Fh
0x18000eec8  and     edx, 80h
0x18000eece  mov     ecx, r8d
0x18000eed1  mov     r15d, 40h ; '@'
0x18000eed7  and     ecx, 3
0x18000eeda  and     eax, r15d
0x18000eedd  shl     ecx, 2
0x18000eee0  or      ecx, eax
0x18000eee2  shl     ecx, 2
0x18000eee5  or      ecx, edx
0x18000eee7  lea     edi, ds:0[rcx*8]
0x18000eeee  test    r8d, r8d
0x18000eef1  jnz     short loc_18000EEF8
0x18000eef3  mov     eax, r15d
0x18000eef6  jmp     short loc_18000EF02
0x18000eef8  xor     eax, eax
0x18000eefa  cmp     r8d, 2
0x18000eefe  cmovz   eax, r15d
0x18000ef02  or      edi, eax
0x18000ef04  mov     eax, [rbx]
0x18000ef06  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ef0b  mov     edx, eax
0x18000ef0d  mov     [rbx], eax
0x18000ef0f  jz      short loc_18000EF3B
0x18000ef11  test    dl, 2
0x18000ef14  jnz     short loc_18000EF3B
0x18000ef16  xor     eax, edi
0x18000ef18  and     eax, 180h
0x18000ef1d  xor     eax, edx
0x18000ef1f  mov     ecx, eax
0x18000ef21  xor     ecx, edi
0x18000ef23  and     ecx, r15d
0x18000ef26  xor     ecx, eax
0x18000ef28  or      ecx, 1
0x18000ef2b  mov     eax, ecx
0x18000ef2d  xor     eax, edi
0x18000ef2f  and     eax, 800h
0x18000ef34  xor     eax, ecx
0x18000ef36  or      eax, 2
0x18000ef39  mov     [rbx], eax
0x18000ef3b  mov     r8d, edx
0x18000ef3e  mov     ecx, eax
0x18000ef40  and     r8d, 4
0x18000ef44  jnz     short loc_18000EF55
0x18000ef46  xor     ecx, edi
0x18000ef48  and     ecx, 400h
0x18000ef4e  xor     ecx, eax
0x18000ef50  or      ecx, 4
0x18000ef53  mov     [rbx], ecx
0x18000ef55  mov     eax, edx
0x18000ef57  lock cmpxchg [rsi], ecx
0x18000ef5b  jnz     short loc_18000EF06
0x18000ef5d  test    r8d, r8d
0x18000ef60  jnz     short loc_18000EF72
0x18000ef62  mov     r8d, ebp
0x18000ef65  mov     edx, 3
0x18000ef6a  mov     rcx, rsi
0x18000ef6d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ef72  test    byte ptr [rbx], 2
0x18000ef75  jnz     short loc_18000EF9B
0x18000ef77  mov     eax, [rbx]
0x18000ef79  xor     eax, edi
0x18000ef7b  and     eax, 180h
0x18000ef80  xor     eax, [rbx]
0x18000ef82  mov     ecx, eax
0x18000ef84  xor     ecx, edi
0x18000ef86  and     ecx, r15d
0x18000ef89  xor     ecx, eax
0x18000ef8b  or      ecx, 1
0x18000ef8e  mov     eax, ecx
0x18000ef90  xor     eax, edi
0x18000ef92  and     eax, 800h
0x18000ef97  xor     eax, ecx
0x18000ef99  mov     [rbx], eax
0x18000ef9b  mov     rbp, [rsp+38h+arg_10]
0x18000efa0  mov     rax, rbx
0x18000efa3  mov     rbx, [rsp+38h+arg_8]
0x18000efa8  add     rsp, 20h
0x18000efac  pop     r15
0x18000efae  pop     rdi
0x18000efaf  pop     rsi
0x18000efb0  retn
```
