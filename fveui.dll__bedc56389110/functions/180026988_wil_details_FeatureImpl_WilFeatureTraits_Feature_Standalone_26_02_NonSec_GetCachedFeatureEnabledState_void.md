# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180026988`
- end: `0x180026ae0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027250`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x18002331c`
- `0x180026988`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E287E,
                            3u,
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
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
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
              (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v5);
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
0x180026988  mov     [rsp+arg_8], rbx
0x18002698d  mov     [rsp+arg_10], rbp
0x180026992  mov     [rsp+arg_0], rcx
0x180026997  push    rsi
0x180026998  push    rdi
0x180026999  push    r15
0x18002699b  sub     rsp, 20h
0x18002699f  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x1800269a6  mov     rbx, rdx
0x1800269a9  mov     qword ptr [rdx], 0
0x1800269b0  mov     eax, [rsi]
0x1800269b2  mov     [rdx], eax
0x1800269b4  and     eax, 6
0x1800269b7  cmp     al, 6
0x1800269b9  jz      loc_180026ACA
0x1800269bf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800269c4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800269c9  mov     dword ptr [rsp+38h+arg_0], 0
0x1800269d1  mov     edx, 3; unsigned int
0x1800269d6  mov     ecx, 37E287Eh; this
0x1800269db  mov     ebp, eax
0x1800269dd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800269e2  mov     r8d, eax
0x1800269e5  mov     ecx, eax
0x1800269e7  and     r8d, 0FFFFFF3Fh
0x1800269ee  and     eax, 80h
0x1800269f3  mov     edx, r8d
0x1800269f6  mov     r15d, 40h ; '@'
0x1800269fc  and     edx, 3
0x1800269ff  and     ecx, r15d
0x180026a02  shl     edx, 2
0x180026a05  or      edx, ecx
0x180026a07  shl     edx, 2
0x180026a0a  or      edx, eax
0x180026a0c  lea     edi, ds:0[rdx*8]
0x180026a13  test    r8d, r8d
0x180026a16  jnz     short loc_180026A1D
0x180026a18  mov     eax, r15d
0x180026a1b  jmp     short loc_180026A27
0x180026a1d  xor     eax, eax
0x180026a1f  cmp     r8d, 2
0x180026a23  cmovz   eax, r15d
0x180026a27  or      edi, eax
0x180026a29  mov     eax, [rbx]
0x180026a2b  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026a30  mov     edx, eax
0x180026a32  mov     [rbx], eax
0x180026a34  jz      short loc_180026A64
0x180026a36  test    dl, 2
0x180026a39  jnz     short loc_180026A64
0x180026a3b  mov     eax, edi
0x180026a3d  xor     eax, edx
0x180026a3f  and     eax, 180h
0x180026a44  xor     eax, edx
0x180026a46  mov     ecx, eax
0x180026a48  xor     ecx, edi
0x180026a4a  and     ecx, r15d
0x180026a4d  xor     ecx, eax
0x180026a4f  or      ecx, 1
0x180026a52  mov     eax, ecx
0x180026a54  xor     eax, edi
0x180026a56  and     eax, 800h
0x180026a5b  xor     eax, ecx
0x180026a5d  or      eax, 2
0x180026a60  mov     [rbx], eax
0x180026a62  jmp     short loc_180026A66
0x180026a64  mov     eax, edx
0x180026a66  mov     r8d, edx
0x180026a69  and     r8d, 4
0x180026a6d  jnz     short loc_180026A82
0x180026a6f  mov     ecx, edi
0x180026a71  xor     ecx, eax
0x180026a73  and     ecx, 400h
0x180026a79  xor     ecx, eax
0x180026a7b  or      ecx, 4
0x180026a7e  mov     [rbx], ecx
0x180026a80  jmp     short loc_180026A84
0x180026a82  mov     ecx, eax
0x180026a84  mov     eax, edx
0x180026a86  lock cmpxchg [rsi], ecx
0x180026a8a  jnz     short loc_180026A2B
0x180026a8c  test    r8d, r8d
0x180026a8f  jnz     short loc_180026AA1
0x180026a91  mov     r8d, ebp
0x180026a94  mov     edx, 3
0x180026a99  mov     rcx, rsi
0x180026a9c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180026aa1  test    byte ptr [rbx], 2
0x180026aa4  jnz     short loc_180026ACA
0x180026aa6  mov     eax, [rbx]
0x180026aa8  xor     eax, edi
0x180026aaa  and     eax, 180h
0x180026aaf  xor     eax, [rbx]
0x180026ab1  mov     ecx, eax
0x180026ab3  xor     ecx, edi
0x180026ab5  and     ecx, r15d
0x180026ab8  xor     ecx, eax
0x180026aba  or      ecx, 1
0x180026abd  mov     eax, ecx
0x180026abf  xor     eax, edi
0x180026ac1  and     eax, 800h
0x180026ac6  xor     eax, ecx
0x180026ac8  mov     [rbx], eax
0x180026aca  mov     rbp, [rsp+38h+arg_10]
0x180026acf  mov     rax, rbx
0x180026ad2  mov     rbx, [rsp+38h+arg_8]
0x180026ad7  add     rsp, 20h
0x180026adb  pop     r15
0x180026add  pop     rdi
0x180026ade  pop     rsi
0x180026adf  retn
```
