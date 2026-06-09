# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCachedFeatureEnabledState(void)

- ea: `0x180008aa0`
- end: `0x180008c6d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmersiveColorFight@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011ff4`

## callees

- `0x1800084b4`
- `0x180008aa0`
- `0x1800113c4`
- `0x1800121cc`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmersiveColorFight>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_ImmersiveColorFight__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ImmersiveColorFight__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(54663121, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ImmersiveColorFight__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ImmersiveColorFight__descriptor, 3, v4);
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
0x180008aa0  mov     [rsp+arg_0], rcx
0x180008aa5  push    rbx
0x180008aa6  push    rbp
0x180008aa7  push    rsi
0x180008aa8  push    rdi
0x180008aa9  push    r12
0x180008aab  push    r14
0x180008aad  sub     rsp, 28h
0x180008ab1  mov     r14, cs:Feature_ImmersiveColorFight__descriptor
0x180008ab8  mov     rdi, rdx
0x180008abb  mov     qword ptr [rdx], 0
0x180008ac2  mov     eax, [r14]
0x180008ac5  mov     [rdx], eax
0x180008ac7  and     eax, 6
0x180008aca  cmp     al, 6
0x180008acc  jz      loc_180008C5D
0x180008ad2  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008ad7  mov     ebp, eax
0x180008ad9  mov     dword ptr [rsp+58h+arg_0], 0
0x180008ae1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008ae8  test    rax, rax
0x180008aeb  jz      short loc_180008B05
0x180008aed  lea     r8, [rsp+58h+arg_0]
0x180008af2  mov     edx, 3
0x180008af7  mov     ecx, 34217D1h
0x180008afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b01  mov     edx, eax
0x180008b03  jmp     short loc_180008B13
0x180008b05  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008b0c  test    rax, rax
0x180008b0f  jnz     short loc_180008AED
0x180008b11  xor     edx, edx
0x180008b13  mov     r8d, edx
0x180008b16  mov     eax, edx
0x180008b18  and     r8d, 0FFFFFF3Fh
0x180008b1f  and     edx, 80h
0x180008b25  mov     ecx, r8d
0x180008b28  mov     r12d, 40h ; '@'
0x180008b2e  and     ecx, 3
0x180008b31  and     eax, r12d
0x180008b34  shl     ecx, 2
0x180008b37  or      ecx, eax
0x180008b39  shl     ecx, 2
0x180008b3c  or      ecx, edx
0x180008b3e  lea     ebx, ds:0[rcx*8]
0x180008b45  test    r8d, r8d
0x180008b48  jnz     short loc_180008B4F
0x180008b4a  mov     eax, r12d
0x180008b4d  jmp     short loc_180008B59
0x180008b4f  xor     eax, eax
0x180008b51  cmp     r8d, 2
0x180008b55  cmovz   eax, r12d
0x180008b59  or      ebx, eax
0x180008b5b  mov     ecx, 0C00h
0x180008b60  mov     eax, ebx
0x180008b62  and     eax, ecx
0x180008b64  cmp     eax, ecx
0x180008b66  jnz     short loc_180008B6D
0x180008b68  mov     sil, 1
0x180008b6b  jmp     short loc_180008B75
0x180008b6d  xor     sil, sil
0x180008b70  test    r12b, bl
0x180008b73  jz      short loc_180008B90
0x180008b75  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180008b7c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180008b81  test    sil, sil
0x180008b84  jz      short loc_180008B92
0x180008b86  test    al, al
0x180008b88  jnz     short loc_180008B92
0x180008b8a  btr     ebx, 0Ah
0x180008b8e  jmp     short loc_180008B92
0x180008b90  xor     al, al
0x180008b92  test    r12b, bl
0x180008b95  jz      short loc_180008BA2
0x180008b97  test    al, al
0x180008b99  jz      short loc_180008BA2
0x180008b9b  mov     esi, 1
0x180008ba0  jmp     short loc_180008BA4
0x180008ba2  xor     esi, esi
0x180008ba4  mov     eax, [rdi]
0x180008ba6  or      esi, ebx
0x180008ba8  mov     ebx, 180h
0x180008bad  cmp     dword ptr [rsp+58h+arg_0], 0
0x180008bb2  mov     edx, eax
0x180008bb4  mov     [rdi], eax
0x180008bb6  jz      short loc_180008BF0
0x180008bb8  test    dl, 2
0x180008bbb  jnz     short loc_180008BF0
0x180008bbd  mov     eax, esi
0x180008bbf  xor     eax, edx
0x180008bc1  and     eax, ebx
0x180008bc3  xor     eax, edx
0x180008bc5  mov     ecx, eax
0x180008bc7  xor     ecx, esi
0x180008bc9  and     ecx, r12d
0x180008bcc  xor     ecx, eax
0x180008bce  mov     eax, ecx
0x180008bd0  xor     eax, esi
0x180008bd2  and     eax, 1
0x180008bd5  xor     eax, ecx
0x180008bd7  mov     r8d, eax
0x180008bda  xor     r8d, esi
0x180008bdd  and     r8d, 800h
0x180008be4  xor     r8d, eax
0x180008be7  or      r8d, 2
0x180008beb  mov     [rdi], r8d
0x180008bee  jmp     short loc_180008BF3
0x180008bf0  mov     r8d, edx
0x180008bf3  mov     r9d, edx
0x180008bf6  and     r9d, 4
0x180008bfa  jnz     short loc_180008C11
0x180008bfc  mov     ecx, esi
0x180008bfe  xor     ecx, r8d
0x180008c01  and     ecx, 400h
0x180008c07  xor     ecx, r8d
0x180008c0a  or      ecx, 4
0x180008c0d  mov     [rdi], ecx
0x180008c0f  jmp     short loc_180008C14
0x180008c11  mov     ecx, r8d
0x180008c14  mov     eax, edx
0x180008c16  lock cmpxchg [r14], ecx
0x180008c1b  jnz     short loc_180008BAD
0x180008c1d  test    r9d, r9d
0x180008c20  jnz     short loc_180008C31
0x180008c22  mov     r8d, ebp
0x180008c25  lea     edx, [r9+3]
0x180008c29  mov     rcx, r14
0x180008c2c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008c31  test    byte ptr [rdi], 2
0x180008c34  jnz     short loc_180008C5D
0x180008c36  mov     eax, [rdi]
0x180008c38  xor     eax, esi
0x180008c3a  and     eax, ebx
0x180008c3c  xor     eax, [rdi]
0x180008c3e  mov     ecx, eax
0x180008c40  xor     ecx, esi
0x180008c42  and     ecx, r12d
0x180008c45  xor     ecx, eax
0x180008c47  mov     edx, ecx
0x180008c49  xor     edx, esi
0x180008c4b  and     edx, 1
0x180008c4e  xor     edx, ecx
0x180008c50  mov     eax, edx
0x180008c52  xor     eax, esi
0x180008c54  and     eax, 800h
0x180008c59  xor     eax, edx
0x180008c5b  mov     [rdi], eax
0x180008c5d  mov     rax, rdi
0x180008c60  add     rsp, 28h
0x180008c64  pop     r14
0x180008c66  pop     r12
0x180008c68  pop     rdi
0x180008c69  pop     rsi
0x180008c6a  pop     rbp
0x180008c6b  pop     rbx
0x180008c6c  retn
```
