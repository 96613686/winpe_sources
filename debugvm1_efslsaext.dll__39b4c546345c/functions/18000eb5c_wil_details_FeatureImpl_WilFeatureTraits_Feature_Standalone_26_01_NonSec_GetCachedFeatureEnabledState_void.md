# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000eb5c`
- end: `0x18000ecc9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f7c0`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000eb5c`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
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
0x18000eb5c  mov     [rsp+arg_8], rbx
0x18000eb61  mov     [rsp+arg_10], rbp
0x18000eb66  mov     [rsp+arg_0], rcx
0x18000eb6b  push    rsi
0x18000eb6c  push    rdi
0x18000eb6d  push    r15
0x18000eb6f  sub     rsp, 20h
0x18000eb73  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000eb7a  mov     rbx, rdx
0x18000eb7d  mov     qword ptr [rdx], 0
0x18000eb84  mov     eax, [rsi]
0x18000eb86  mov     [rdx], eax
0x18000eb88  and     eax, 6
0x18000eb8b  cmp     al, 6
0x18000eb8d  jz      loc_18000ECB3
0x18000eb93  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000eb98  mov     ebp, eax
0x18000eb9a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000eba2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000eba9  test    rax, rax
0x18000ebac  jz      short loc_18000EBC6
0x18000ebae  lea     r8, [rsp+38h+arg_0]
0x18000ebb3  mov     edx, 3
0x18000ebb8  mov     ecx, 37E286Ch
0x18000ebbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebc2  mov     edx, eax
0x18000ebc4  jmp     short loc_18000EBD4
0x18000ebc6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ebcd  test    rax, rax
0x18000ebd0  jnz     short loc_18000EBAE
0x18000ebd2  xor     edx, edx
0x18000ebd4  mov     r8d, edx
0x18000ebd7  mov     eax, edx
0x18000ebd9  and     r8d, 0FFFFFF3Fh
0x18000ebe0  and     edx, 80h
0x18000ebe6  mov     ecx, r8d
0x18000ebe9  mov     r15d, 40h ; '@'
0x18000ebef  and     ecx, 3
0x18000ebf2  and     eax, r15d
0x18000ebf5  shl     ecx, 2
0x18000ebf8  or      ecx, eax
0x18000ebfa  shl     ecx, 2
0x18000ebfd  or      ecx, edx
0x18000ebff  lea     edi, ds:0[rcx*8]
0x18000ec06  test    r8d, r8d
0x18000ec09  jnz     short loc_18000EC10
0x18000ec0b  mov     eax, r15d
0x18000ec0e  jmp     short loc_18000EC1A
0x18000ec10  xor     eax, eax
0x18000ec12  cmp     r8d, 2
0x18000ec16  cmovz   eax, r15d
0x18000ec1a  or      edi, eax
0x18000ec1c  mov     eax, [rbx]
0x18000ec1e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ec23  mov     edx, eax
0x18000ec25  mov     [rbx], eax
0x18000ec27  jz      short loc_18000EC53
0x18000ec29  test    dl, 2
0x18000ec2c  jnz     short loc_18000EC53
0x18000ec2e  xor     eax, edi
0x18000ec30  and     eax, 180h
0x18000ec35  xor     eax, edx
0x18000ec37  mov     ecx, eax
0x18000ec39  xor     ecx, edi
0x18000ec3b  and     ecx, r15d
0x18000ec3e  xor     ecx, eax
0x18000ec40  or      ecx, 1
0x18000ec43  mov     eax, ecx
0x18000ec45  xor     eax, edi
0x18000ec47  and     eax, 800h
0x18000ec4c  xor     eax, ecx
0x18000ec4e  or      eax, 2
0x18000ec51  mov     [rbx], eax
0x18000ec53  mov     r8d, edx
0x18000ec56  mov     ecx, eax
0x18000ec58  and     r8d, 4
0x18000ec5c  jnz     short loc_18000EC6D
0x18000ec5e  xor     ecx, edi
0x18000ec60  and     ecx, 400h
0x18000ec66  xor     ecx, eax
0x18000ec68  or      ecx, 4
0x18000ec6b  mov     [rbx], ecx
0x18000ec6d  mov     eax, edx
0x18000ec6f  lock cmpxchg [rsi], ecx
0x18000ec73  jnz     short loc_18000EC1E
0x18000ec75  test    r8d, r8d
0x18000ec78  jnz     short loc_18000EC8A
0x18000ec7a  mov     r8d, ebp
0x18000ec7d  mov     edx, 3
0x18000ec82  mov     rcx, rsi
0x18000ec85  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ec8a  test    byte ptr [rbx], 2
0x18000ec8d  jnz     short loc_18000ECB3
0x18000ec8f  mov     eax, [rbx]
0x18000ec91  xor     eax, edi
0x18000ec93  and     eax, 180h
0x18000ec98  xor     eax, [rbx]
0x18000ec9a  mov     ecx, eax
0x18000ec9c  xor     ecx, edi
0x18000ec9e  and     ecx, r15d
0x18000eca1  xor     ecx, eax
0x18000eca3  or      ecx, 1
0x18000eca6  mov     eax, ecx
0x18000eca8  xor     eax, edi
0x18000ecaa  and     eax, 800h
0x18000ecaf  xor     eax, ecx
0x18000ecb1  mov     [rbx], eax
0x18000ecb3  mov     rbp, [rsp+38h+arg_10]
0x18000ecb8  mov     rax, rbx
0x18000ecbb  mov     rbx, [rsp+38h+arg_8]
0x18000ecc0  add     rsp, 20h
0x18000ecc4  pop     r15
0x18000ecc6  pop     rdi
0x18000ecc7  pop     rsi
0x18000ecc8  retn
```
