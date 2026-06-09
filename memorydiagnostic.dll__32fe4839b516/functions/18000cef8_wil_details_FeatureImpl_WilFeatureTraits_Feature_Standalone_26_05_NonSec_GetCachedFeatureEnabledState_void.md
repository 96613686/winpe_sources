# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_05_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000cef8`
- end: `0x18000d069`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_05_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d1e4`

## callees

- `0x18000ae90`
- `0x18000cef8`
- `0x1800140e0`
- `0x180024010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_05_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 (__fastcall *v6)(__int64, __int64, int *); // rax
  int v7; // edx
  int v8; // edi
  int v9; // edi
  int v10; // eax
  signed __int32 i; // r8d
  bool v12; // zf
  signed __int32 v13; // edx
  int v14; // ecx
  signed __int32 v15; // eax
  int v16; // eax
  int v18; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_05_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_05_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v18 = 0;
    v5 = v4;
    v6 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v6 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v7 = v6(58599563, 3, &v18);
    }
    else
    {
      v7 = 0;
    }
    v8 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( (v7 & 0xFFFFFF3F) == 2 )
        v10 = 64;
      v9 = v10 | v8;
    }
    else
    {
      v9 = v8 | 0x40;
    }
    for ( i = *(_DWORD *)a2; ; i = v15 )
    {
      v12 = v18 == 0;
      v13 = i | 0x40000;
      *(_DWORD *)a2 = i | 0x40000;
      if ( !v12 && (i & 2) == 0 )
      {
        v14 = (i | 0x40000)
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)i)
            & 0x180
            ^ (v9
             ^ (i | 0x40000)
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)i)
             & 0x180)
            & 0x40
            | 1;
        v13 = v14 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v14) & 0x800 | 2;
        *(_DWORD *)a2 = v13;
      }
      if ( (i & 4) == 0 )
      {
        v13 = ((unsigned __int16)v13 ^ (unsigned __int16)v9) & 0x400 ^ v13 | 4;
        *(_DWORD *)a2 = v13;
      }
      v15 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_05_NonSec__descriptor, v13, i);
      if ( i == v15 )
        break;
    }
    if ( (i & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_05_NonSec__descriptor, 3, v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
    {
      v16 = *(_DWORD *)a2 ^ ((unsigned __int16)v9 ^ (unsigned __int16)*(_DWORD *)a2) & 0x180;
      *(_DWORD *)a2 = (v16 ^ (v16 ^ v9) & 0x40 | 1)
                    ^ ((unsigned __int16)v9
                     ^ ((unsigned __int16)(v16 ^ (v16 ^ v9) & 0x40) | 1))
                    & 0x800;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000cef8  mov     [rsp+arg_0], rbx
0x18000cefd  mov     [rsp+arg_10], rbp
0x18000cf02  push    rsi
0x18000cf03  push    rdi
0x18000cf04  push    r15
0x18000cf06  sub     rsp, 20h
0x18000cf0a  and     qword ptr [rdx], 0
0x18000cf0e  mov     rbx, rdx
0x18000cf11  mov     rsi, cs:Feature_Standalone_26_05_NonSec__descriptor
0x18000cf18  mov     eax, [rsi]
0x18000cf1a  mov     [rdx], eax
0x18000cf1c  and     eax, 6
0x18000cf1f  cmp     al, 6
0x18000cf21  jz      loc_18000D052
0x18000cf27  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000cf2c  and     [rsp+38h+arg_8], 0
0x18000cf31  mov     ebp, eax
0x18000cf33  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000cf3a  test    rax, rax
0x18000cf3d  jz      short loc_18000CF57
0x18000cf3f  lea     r8, [rsp+38h+arg_8]
0x18000cf44  mov     edx, 3
0x18000cf49  mov     ecx, 37E288Bh
0x18000cf4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf53  mov     edx, eax
0x18000cf55  jmp     short loc_18000CF65
0x18000cf57  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000cf5e  test    rax, rax
0x18000cf61  jnz     short loc_18000CF3F
0x18000cf63  xor     edx, edx
0x18000cf65  mov     r8d, edx
0x18000cf68  mov     eax, edx
0x18000cf6a  and     r8d, 0FFFFFF3Fh
0x18000cf71  and     edx, 80h
0x18000cf77  mov     ecx, r8d
0x18000cf7a  mov     r15d, 40h ; '@'
0x18000cf80  and     ecx, 3
0x18000cf83  and     eax, r15d
0x18000cf86  shl     ecx, 2
0x18000cf89  or      ecx, eax
0x18000cf8b  shl     ecx, 2
0x18000cf8e  or      ecx, edx
0x18000cf90  lea     edi, ds:0[rcx*8]
0x18000cf97  test    r8d, r8d
0x18000cf9a  jnz     short loc_18000CFA1
0x18000cf9c  or      edi, r15d
0x18000cf9f  jmp     short loc_18000CFAD
0x18000cfa1  xor     eax, eax
0x18000cfa3  cmp     r8d, 2
0x18000cfa7  cmovz   eax, r15d
0x18000cfab  or      edi, eax
0x18000cfad  mov     r8d, [rbx]
0x18000cfb0  mov     ecx, r8d
0x18000cfb3  bts     ecx, 12h
0x18000cfb7  cmp     [rsp+38h+arg_8], 0
0x18000cfbc  mov     edx, ecx
0x18000cfbe  mov     [rbx], ecx
0x18000cfc0  jz      short loc_18000CFEF
0x18000cfc2  test    cl, 2
0x18000cfc5  jnz     short loc_18000CFEF
0x18000cfc7  mov     eax, ecx
0x18000cfc9  xor     eax, edi
0x18000cfcb  and     eax, 180h
0x18000cfd0  xor     eax, ecx
0x18000cfd2  mov     ecx, eax
0x18000cfd4  xor     ecx, edi
0x18000cfd6  and     ecx, r15d
0x18000cfd9  xor     ecx, eax
0x18000cfdb  or      ecx, 1
0x18000cfde  mov     edx, ecx
0x18000cfe0  xor     edx, edi
0x18000cfe2  and     edx, 800h
0x18000cfe8  xor     edx, ecx
0x18000cfea  or      edx, 2
0x18000cfed  mov     [rbx], edx
0x18000cfef  test    r8b, 4
0x18000cff3  jnz     short loc_18000D005
0x18000cff5  mov     eax, edi
0x18000cff7  xor     eax, edx
0x18000cff9  and     eax, 400h
0x18000cffe  xor     edx, eax
0x18000d000  or      edx, 4
0x18000d003  mov     [rbx], edx
0x18000d005  mov     eax, r8d
0x18000d008  lock cmpxchg [rsi], edx
0x18000d00c  jz      short loc_18000D013
0x18000d00e  mov     r8d, eax
0x18000d011  jmp     short loc_18000CFB0
0x18000d013  test    r8b, 4
0x18000d017  jnz     short loc_18000D029
0x18000d019  mov     r8d, ebp
0x18000d01c  mov     edx, 3
0x18000d021  mov     rcx, rsi
0x18000d024  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000d029  test    byte ptr [rbx], 2
0x18000d02c  jnz     short loc_18000D052
0x18000d02e  mov     eax, [rbx]
0x18000d030  mov     ecx, edi
0x18000d032  xor     eax, edi
0x18000d034  and     eax, 180h
0x18000d039  xor     eax, [rbx]
0x18000d03b  xor     ecx, eax
0x18000d03d  and     ecx, r15d
0x18000d040  xor     ecx, eax
0x18000d042  or      ecx, 1
0x18000d045  mov     eax, ecx
0x18000d047  xor     eax, edi
0x18000d049  and     eax, 800h
0x18000d04e  xor     eax, ecx
0x18000d050  mov     [rbx], eax
0x18000d052  mov     rbp, [rsp+38h+arg_10]
0x18000d057  mov     rax, rbx
0x18000d05a  mov     rbx, [rsp+38h+arg_0]
0x18000d05f  add     rsp, 20h
0x18000d063  pop     r15
0x18000d065  pop     rdi
0x18000d066  pop     rsi
0x18000d067  retn
```
