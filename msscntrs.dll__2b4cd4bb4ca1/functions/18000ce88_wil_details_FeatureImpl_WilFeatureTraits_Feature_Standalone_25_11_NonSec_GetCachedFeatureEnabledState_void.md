# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ce88`
- end: `0x18000cff5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012f40`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000ce88`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036797, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v4);
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
0x18000ce88  mov     [rsp+arg_8], rbx
0x18000ce8d  mov     [rsp+arg_10], rbp
0x18000ce92  mov     [rsp+arg_0], rcx
0x18000ce97  push    rsi
0x18000ce98  push    rdi
0x18000ce99  push    r15
0x18000ce9b  sub     rsp, 20h
0x18000ce9f  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000cea6  mov     rbx, rdx
0x18000cea9  mov     qword ptr [rdx], 0
0x18000ceb0  mov     eax, [rsi]
0x18000ceb2  mov     [rdx], eax
0x18000ceb4  and     eax, 6
0x18000ceb7  cmp     al, 6
0x18000ceb9  jz      loc_18000CFDF
0x18000cebf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000cec4  mov     ebp, eax
0x18000cec6  mov     dword ptr [rsp+38h+arg_0], 0
0x18000cece  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ced5  test    rax, rax
0x18000ced8  jz      short loc_18000CEF2
0x18000ceda  lea     r8, [rsp+38h+arg_0]
0x18000cedf  mov     edx, 3
0x18000cee4  mov     ecx, 2AF34FDh
0x18000cee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceee  mov     edx, eax
0x18000cef0  jmp     short loc_18000CF00
0x18000cef2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000cef9  test    rax, rax
0x18000cefc  jnz     short loc_18000CEDA
0x18000cefe  xor     edx, edx
0x18000cf00  mov     r8d, edx
0x18000cf03  mov     eax, edx
0x18000cf05  and     r8d, 0FFFFFF3Fh
0x18000cf0c  and     edx, 80h
0x18000cf12  mov     ecx, r8d
0x18000cf15  mov     r15d, 40h ; '@'
0x18000cf1b  and     ecx, 3
0x18000cf1e  and     eax, r15d
0x18000cf21  shl     ecx, 2
0x18000cf24  or      ecx, eax
0x18000cf26  shl     ecx, 2
0x18000cf29  or      ecx, edx
0x18000cf2b  lea     edi, ds:0[rcx*8]
0x18000cf32  test    r8d, r8d
0x18000cf35  jnz     short loc_18000CF3C
0x18000cf37  mov     eax, r15d
0x18000cf3a  jmp     short loc_18000CF46
0x18000cf3c  xor     eax, eax
0x18000cf3e  cmp     r8d, 2
0x18000cf42  cmovz   eax, r15d
0x18000cf46  or      edi, eax
0x18000cf48  mov     eax, [rbx]
0x18000cf4a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000cf4f  mov     edx, eax
0x18000cf51  mov     [rbx], eax
0x18000cf53  jz      short loc_18000CF7F
0x18000cf55  test    dl, 2
0x18000cf58  jnz     short loc_18000CF7F
0x18000cf5a  xor     eax, edi
0x18000cf5c  and     eax, 180h
0x18000cf61  xor     eax, edx
0x18000cf63  mov     ecx, eax
0x18000cf65  xor     ecx, edi
0x18000cf67  and     ecx, r15d
0x18000cf6a  xor     ecx, eax
0x18000cf6c  or      ecx, 1
0x18000cf6f  mov     eax, ecx
0x18000cf71  xor     eax, edi
0x18000cf73  and     eax, 800h
0x18000cf78  xor     eax, ecx
0x18000cf7a  or      eax, 2
0x18000cf7d  mov     [rbx], eax
0x18000cf7f  mov     r8d, edx
0x18000cf82  mov     ecx, eax
0x18000cf84  and     r8d, 4
0x18000cf88  jnz     short loc_18000CF99
0x18000cf8a  xor     ecx, edi
0x18000cf8c  and     ecx, 400h
0x18000cf92  xor     ecx, eax
0x18000cf94  or      ecx, 4
0x18000cf97  mov     [rbx], ecx
0x18000cf99  mov     eax, edx
0x18000cf9b  lock cmpxchg [rsi], ecx
0x18000cf9f  jnz     short loc_18000CF4A
0x18000cfa1  test    r8d, r8d
0x18000cfa4  jnz     short loc_18000CFB6
0x18000cfa6  mov     r8d, ebp
0x18000cfa9  mov     edx, 3
0x18000cfae  mov     rcx, rsi
0x18000cfb1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000cfb6  test    byte ptr [rbx], 2
0x18000cfb9  jnz     short loc_18000CFDF
0x18000cfbb  mov     eax, [rbx]
0x18000cfbd  xor     eax, edi
0x18000cfbf  and     eax, 180h
0x18000cfc4  xor     eax, [rbx]
0x18000cfc6  mov     ecx, eax
0x18000cfc8  xor     ecx, edi
0x18000cfca  and     ecx, r15d
0x18000cfcd  xor     ecx, eax
0x18000cfcf  or      ecx, 1
0x18000cfd2  mov     eax, ecx
0x18000cfd4  xor     eax, edi
0x18000cfd6  and     eax, 800h
0x18000cfdb  xor     eax, ecx
0x18000cfdd  mov     [rbx], eax
0x18000cfdf  mov     rbp, [rsp+38h+arg_10]
0x18000cfe4  mov     rax, rbx
0x18000cfe7  mov     rbx, [rsp+38h+arg_8]
0x18000cfec  add     rsp, 20h
0x18000cff0  pop     r15
0x18000cff2  pop     rdi
0x18000cff3  pop     rsi
0x18000cff4  retn
```
