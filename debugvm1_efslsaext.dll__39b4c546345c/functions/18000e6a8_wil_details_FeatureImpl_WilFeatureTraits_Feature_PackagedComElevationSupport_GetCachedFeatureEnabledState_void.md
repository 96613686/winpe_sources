# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e6a8`
- end: `0x18000e86e`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011594`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000e6a8`
- `0x1800116a4`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_PackagedComElevationSupport__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_PackagedComElevationSupport__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(51593804, 3, &v20);
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
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled();
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_17;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = *(_DWORD *)a2;
  v13 = v8 | v11;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( v14 || (v12 & 2) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v16 = v12
          ^ (v12
           ^ v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ (v12
            ^ v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_PackagedComElevationSupport__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_PackagedComElevationSupport__descriptor,
      3,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v13
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v13
                    ^ *(_DWORD *)a2
                    ^ (v13
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v13
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v13
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v13
                       ^ *(_BYTE *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x18000e6a8  mov     [rsp+arg_0], rcx
0x18000e6ad  push    rbx
0x18000e6ae  push    rbp
0x18000e6af  push    rsi
0x18000e6b0  push    rdi
0x18000e6b1  push    r12
0x18000e6b3  push    r14
0x18000e6b5  sub     rsp, 28h
0x18000e6b9  mov     r14, cs:Feature_PackagedComElevationSupport__descriptor
0x18000e6c0  mov     rdi, rdx
0x18000e6c3  mov     qword ptr [rdx], 0
0x18000e6ca  mov     eax, [r14]
0x18000e6cd  mov     [rdx], eax
0x18000e6cf  and     eax, 6
0x18000e6d2  cmp     al, 6
0x18000e6d4  jz      loc_18000E85E
0x18000e6da  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e6df  mov     ebp, eax
0x18000e6e1  mov     dword ptr [rsp+58h+arg_0], 0
0x18000e6e9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e6f0  test    rax, rax
0x18000e6f3  jz      short loc_18000E70D
0x18000e6f5  lea     r8, [rsp+58h+arg_0]
0x18000e6fa  mov     edx, 3
0x18000e6ff  mov     ecx, 313424Ch
0x18000e704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e709  mov     edx, eax
0x18000e70b  jmp     short loc_18000E71B
0x18000e70d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e714  test    rax, rax
0x18000e717  jnz     short loc_18000E6F5
0x18000e719  xor     edx, edx
0x18000e71b  mov     r8d, edx
0x18000e71e  mov     eax, edx
0x18000e720  and     r8d, 0FFFFFF3Fh
0x18000e727  and     edx, 80h
0x18000e72d  mov     ecx, r8d
0x18000e730  mov     r12d, 40h ; '@'
0x18000e736  and     ecx, 3
0x18000e739  and     eax, r12d
0x18000e73c  shl     ecx, 2
0x18000e73f  or      ecx, eax
0x18000e741  shl     ecx, 2
0x18000e744  or      ecx, edx
0x18000e746  lea     ebx, ds:0[rcx*8]
0x18000e74d  test    r8d, r8d
0x18000e750  jnz     short loc_18000E757
0x18000e752  mov     eax, r12d
0x18000e755  jmp     short loc_18000E761
0x18000e757  xor     eax, eax
0x18000e759  cmp     r8d, 2
0x18000e75d  cmovz   eax, r12d
0x18000e761  or      ebx, eax
0x18000e763  mov     ecx, 0C00h
0x18000e768  mov     eax, ebx
0x18000e76a  and     eax, ecx
0x18000e76c  cmp     eax, ecx
0x18000e76e  jnz     short loc_18000E775
0x18000e770  mov     sil, 1
0x18000e773  jmp     short loc_18000E77D
0x18000e775  xor     sil, sil
0x18000e778  test    r12b, bl
0x18000e77b  jz      short loc_18000E791
0x18000e77d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18000e782  test    sil, sil
0x18000e785  jz      short loc_18000E793
0x18000e787  test    al, al
0x18000e789  jnz     short loc_18000E793
0x18000e78b  btr     ebx, 0Ah
0x18000e78f  jmp     short loc_18000E793
0x18000e791  xor     al, al
0x18000e793  test    r12b, bl
0x18000e796  jz      short loc_18000E7A3
0x18000e798  test    al, al
0x18000e79a  jz      short loc_18000E7A3
0x18000e79c  mov     esi, 1
0x18000e7a1  jmp     short loc_18000E7A5
0x18000e7a3  xor     esi, esi
0x18000e7a5  mov     eax, [rdi]
0x18000e7a7  or      esi, ebx
0x18000e7a9  mov     ebx, 180h
0x18000e7ae  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000e7b3  mov     edx, eax
0x18000e7b5  mov     [rdi], eax
0x18000e7b7  jz      short loc_18000E7F1
0x18000e7b9  test    dl, 2
0x18000e7bc  jnz     short loc_18000E7F1
0x18000e7be  mov     eax, esi
0x18000e7c0  xor     eax, edx
0x18000e7c2  and     eax, ebx
0x18000e7c4  xor     eax, edx
0x18000e7c6  mov     ecx, eax
0x18000e7c8  xor     ecx, esi
0x18000e7ca  and     ecx, r12d
0x18000e7cd  xor     ecx, eax
0x18000e7cf  mov     eax, ecx
0x18000e7d1  xor     eax, esi
0x18000e7d3  and     eax, 1
0x18000e7d6  xor     eax, ecx
0x18000e7d8  mov     r8d, eax
0x18000e7db  xor     r8d, esi
0x18000e7de  and     r8d, 800h
0x18000e7e5  xor     r8d, eax
0x18000e7e8  or      r8d, 2
0x18000e7ec  mov     [rdi], r8d
0x18000e7ef  jmp     short loc_18000E7F4
0x18000e7f1  mov     r8d, edx
0x18000e7f4  mov     r9d, edx
0x18000e7f7  and     r9d, 4
0x18000e7fb  jnz     short loc_18000E812
0x18000e7fd  mov     ecx, esi
0x18000e7ff  xor     ecx, r8d
0x18000e802  and     ecx, 400h
0x18000e808  xor     ecx, r8d
0x18000e80b  or      ecx, 4
0x18000e80e  mov     [rdi], ecx
0x18000e810  jmp     short loc_18000E815
0x18000e812  mov     ecx, r8d
0x18000e815  mov     eax, edx
0x18000e817  lock cmpxchg [r14], ecx
0x18000e81c  jnz     short loc_18000E7AE
0x18000e81e  test    r9d, r9d
0x18000e821  jnz     short loc_18000E832
0x18000e823  mov     r8d, ebp
0x18000e826  lea     edx, [r9+3]
0x18000e82a  mov     rcx, r14
0x18000e82d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e832  test    byte ptr [rdi], 2
0x18000e835  jnz     short loc_18000E85E
0x18000e837  mov     eax, [rdi]
0x18000e839  xor     eax, esi
0x18000e83b  and     eax, ebx
0x18000e83d  xor     eax, [rdi]
0x18000e83f  mov     ecx, eax
0x18000e841  xor     ecx, esi
0x18000e843  and     ecx, r12d
0x18000e846  xor     ecx, eax
0x18000e848  mov     edx, ecx
0x18000e84a  xor     edx, esi
0x18000e84c  and     edx, 1
0x18000e84f  xor     edx, ecx
0x18000e851  mov     eax, edx
0x18000e853  xor     eax, esi
0x18000e855  and     eax, 800h
0x18000e85a  xor     eax, edx
0x18000e85c  mov     [rdi], eax
0x18000e85e  mov     rax, rdi
0x18000e861  add     rsp, 28h
0x18000e865  pop     r14
0x18000e867  pop     r12
0x18000e869  pop     rdi
0x18000e86a  pop     rsi
0x18000e86b  pop     rbp
0x18000e86c  pop     rbx
0x18000e86d  retn
```
