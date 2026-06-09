# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e9e8`
- end: `0x18000eb55`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f6ac`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000e9e8`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x18000e9e8  mov     [rsp+arg_8], rbx
0x18000e9ed  mov     [rsp+arg_10], rbp
0x18000e9f2  mov     [rsp+arg_0], rcx
0x18000e9f7  push    rsi
0x18000e9f8  push    rdi
0x18000e9f9  push    r15
0x18000e9fb  sub     rsp, 20h
0x18000e9ff  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000ea06  mov     rbx, rdx
0x18000ea09  mov     qword ptr [rdx], 0
0x18000ea10  mov     eax, [rsi]
0x18000ea12  mov     [rdx], eax
0x18000ea14  and     eax, 6
0x18000ea17  cmp     al, 6
0x18000ea19  jz      loc_18000EB3F
0x18000ea1f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ea24  mov     ebp, eax
0x18000ea26  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ea2e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ea35  test    rax, rax
0x18000ea38  jz      short loc_18000EA52
0x18000ea3a  lea     r8, [rsp+38h+arg_0]
0x18000ea3f  mov     edx, 3
0x18000ea44  mov     ecx, 2AF34FDh
0x18000ea49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea4e  mov     edx, eax
0x18000ea50  jmp     short loc_18000EA60
0x18000ea52  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ea59  test    rax, rax
0x18000ea5c  jnz     short loc_18000EA3A
0x18000ea5e  xor     edx, edx
0x18000ea60  mov     r8d, edx
0x18000ea63  mov     eax, edx
0x18000ea65  and     r8d, 0FFFFFF3Fh
0x18000ea6c  and     edx, 80h
0x18000ea72  mov     ecx, r8d
0x18000ea75  mov     r15d, 40h ; '@'
0x18000ea7b  and     ecx, 3
0x18000ea7e  and     eax, r15d
0x18000ea81  shl     ecx, 2
0x18000ea84  or      ecx, eax
0x18000ea86  shl     ecx, 2
0x18000ea89  or      ecx, edx
0x18000ea8b  lea     edi, ds:0[rcx*8]
0x18000ea92  test    r8d, r8d
0x18000ea95  jnz     short loc_18000EA9C
0x18000ea97  mov     eax, r15d
0x18000ea9a  jmp     short loc_18000EAA6
0x18000ea9c  xor     eax, eax
0x18000ea9e  cmp     r8d, 2
0x18000eaa2  cmovz   eax, r15d
0x18000eaa6  or      edi, eax
0x18000eaa8  mov     eax, [rbx]
0x18000eaaa  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000eaaf  mov     edx, eax
0x18000eab1  mov     [rbx], eax
0x18000eab3  jz      short loc_18000EADF
0x18000eab5  test    dl, 2
0x18000eab8  jnz     short loc_18000EADF
0x18000eaba  xor     eax, edi
0x18000eabc  and     eax, 180h
0x18000eac1  xor     eax, edx
0x18000eac3  mov     ecx, eax
0x18000eac5  xor     ecx, edi
0x18000eac7  and     ecx, r15d
0x18000eaca  xor     ecx, eax
0x18000eacc  or      ecx, 1
0x18000eacf  mov     eax, ecx
0x18000ead1  xor     eax, edi
0x18000ead3  and     eax, 800h
0x18000ead8  xor     eax, ecx
0x18000eada  or      eax, 2
0x18000eadd  mov     [rbx], eax
0x18000eadf  mov     r8d, edx
0x18000eae2  mov     ecx, eax
0x18000eae4  and     r8d, 4
0x18000eae8  jnz     short loc_18000EAF9
0x18000eaea  xor     ecx, edi
0x18000eaec  and     ecx, 400h
0x18000eaf2  xor     ecx, eax
0x18000eaf4  or      ecx, 4
0x18000eaf7  mov     [rbx], ecx
0x18000eaf9  mov     eax, edx
0x18000eafb  lock cmpxchg [rsi], ecx
0x18000eaff  jnz     short loc_18000EAAA
0x18000eb01  test    r8d, r8d
0x18000eb04  jnz     short loc_18000EB16
0x18000eb06  mov     r8d, ebp
0x18000eb09  mov     edx, 3
0x18000eb0e  mov     rcx, rsi
0x18000eb11  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000eb16  test    byte ptr [rbx], 2
0x18000eb19  jnz     short loc_18000EB3F
0x18000eb1b  mov     eax, [rbx]
0x18000eb1d  xor     eax, edi
0x18000eb1f  and     eax, 180h
0x18000eb24  xor     eax, [rbx]
0x18000eb26  mov     ecx, eax
0x18000eb28  xor     ecx, edi
0x18000eb2a  and     ecx, r15d
0x18000eb2d  xor     ecx, eax
0x18000eb2f  or      ecx, 1
0x18000eb32  mov     eax, ecx
0x18000eb34  xor     eax, edi
0x18000eb36  and     eax, 800h
0x18000eb3b  xor     eax, ecx
0x18000eb3d  mov     [rbx], eax
0x18000eb3f  mov     rbp, [rsp+38h+arg_10]
0x18000eb44  mov     rax, rbx
0x18000eb47  mov     rbx, [rsp+38h+arg_8]
0x18000eb4c  add     rsp, 20h
0x18000eb50  pop     r15
0x18000eb52  pop     rdi
0x18000eb53  pop     rsi
0x18000eb54  retn
```
