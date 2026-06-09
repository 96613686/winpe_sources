# wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b5fc`
- end: `0x18001b7c9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023af4`

## callees

- `0x180009e0c`
- `0x18000bbb0`
- `0x18001b5fc`
- `0x180023c34`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_EapServerTls13__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_EapServerTls13__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60520429, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_EapServerTls13__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_EapServerTls13__descriptor, 3, v4);
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
0x18001b5fc  mov     [rsp+arg_0], rcx
0x18001b601  push    rbx
0x18001b602  push    rbp
0x18001b603  push    rsi
0x18001b604  push    rdi
0x18001b605  push    r12
0x18001b607  push    r14
0x18001b609  sub     rsp, 28h
0x18001b60d  mov     r14, cs:Feature_EapServerTls13__descriptor
0x18001b614  mov     rdi, rdx
0x18001b617  mov     qword ptr [rdx], 0
0x18001b61e  mov     eax, [r14]
0x18001b621  mov     [rdx], eax
0x18001b623  and     eax, 6
0x18001b626  cmp     al, 6
0x18001b628  jz      loc_18001B7B9
0x18001b62e  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b633  mov     ebp, eax
0x18001b635  mov     dword ptr [rsp+58h+arg_0], 0
0x18001b63d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001b644  test    rax, rax
0x18001b647  jz      short loc_18001B661
0x18001b649  lea     r8, [rsp+58h+arg_0]
0x18001b64e  mov     edx, 3
0x18001b653  mov     ecx, 39B77EDh
0x18001b658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b65d  mov     edx, eax
0x18001b65f  jmp     short loc_18001B66F
0x18001b661  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001b668  test    rax, rax
0x18001b66b  jnz     short loc_18001B649
0x18001b66d  xor     edx, edx
0x18001b66f  mov     r8d, edx
0x18001b672  mov     eax, edx
0x18001b674  and     r8d, 0FFFFFF3Fh
0x18001b67b  and     edx, 80h
0x18001b681  mov     ecx, r8d
0x18001b684  mov     r12d, 40h ; '@'
0x18001b68a  and     ecx, 3
0x18001b68d  and     eax, r12d
0x18001b690  shl     ecx, 2
0x18001b693  or      ecx, eax
0x18001b695  shl     ecx, 2
0x18001b698  or      ecx, edx
0x18001b69a  lea     ebx, ds:0[rcx*8]
0x18001b6a1  test    r8d, r8d
0x18001b6a4  jnz     short loc_18001B6AB
0x18001b6a6  mov     eax, r12d
0x18001b6a9  jmp     short loc_18001B6B5
0x18001b6ab  xor     eax, eax
0x18001b6ad  cmp     r8d, 2
0x18001b6b1  cmovz   eax, r12d
0x18001b6b5  or      ebx, eax
0x18001b6b7  mov     ecx, 0C00h
0x18001b6bc  mov     eax, ebx
0x18001b6be  and     eax, ecx
0x18001b6c0  cmp     eax, ecx
0x18001b6c2  jnz     short loc_18001B6C9
0x18001b6c4  mov     sil, 1
0x18001b6c7  jmp     short loc_18001B6D1
0x18001b6c9  xor     sil, sil
0x18001b6cc  test    r12b, bl
0x18001b6cf  jz      short loc_18001B6EC
0x18001b6d1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001b6d8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001b6dd  test    sil, sil
0x18001b6e0  jz      short loc_18001B6EE
0x18001b6e2  test    al, al
0x18001b6e4  jnz     short loc_18001B6EE
0x18001b6e6  btr     ebx, 0Ah
0x18001b6ea  jmp     short loc_18001B6EE
0x18001b6ec  xor     al, al
0x18001b6ee  test    r12b, bl
0x18001b6f1  jz      short loc_18001B6FE
0x18001b6f3  test    al, al
0x18001b6f5  jz      short loc_18001B6FE
0x18001b6f7  mov     esi, 1
0x18001b6fc  jmp     short loc_18001B700
0x18001b6fe  xor     esi, esi
0x18001b700  mov     eax, [rdi]
0x18001b702  or      esi, ebx
0x18001b704  mov     ebx, 180h
0x18001b709  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001b70e  mov     edx, eax
0x18001b710  mov     [rdi], eax
0x18001b712  jz      short loc_18001B74C
0x18001b714  test    dl, 2
0x18001b717  jnz     short loc_18001B74C
0x18001b719  mov     eax, esi
0x18001b71b  xor     eax, edx
0x18001b71d  and     eax, ebx
0x18001b71f  xor     eax, edx
0x18001b721  mov     ecx, eax
0x18001b723  xor     ecx, esi
0x18001b725  and     ecx, r12d
0x18001b728  xor     ecx, eax
0x18001b72a  mov     eax, ecx
0x18001b72c  xor     eax, esi
0x18001b72e  and     eax, 1
0x18001b731  xor     eax, ecx
0x18001b733  mov     r8d, eax
0x18001b736  xor     r8d, esi
0x18001b739  and     r8d, 800h
0x18001b740  xor     r8d, eax
0x18001b743  or      r8d, 2
0x18001b747  mov     [rdi], r8d
0x18001b74a  jmp     short loc_18001B74F
0x18001b74c  mov     r8d, edx
0x18001b74f  mov     r9d, edx
0x18001b752  and     r9d, 4
0x18001b756  jnz     short loc_18001B76D
0x18001b758  mov     ecx, esi
0x18001b75a  xor     ecx, r8d
0x18001b75d  and     ecx, 400h
0x18001b763  xor     ecx, r8d
0x18001b766  or      ecx, 4
0x18001b769  mov     [rdi], ecx
0x18001b76b  jmp     short loc_18001B770
0x18001b76d  mov     ecx, r8d
0x18001b770  mov     eax, edx
0x18001b772  lock cmpxchg [r14], ecx
0x18001b777  jnz     short loc_18001B709
0x18001b779  test    r9d, r9d
0x18001b77c  jnz     short loc_18001B78D
0x18001b77e  mov     r8d, ebp
0x18001b781  lea     edx, [r9+3]
0x18001b785  mov     rcx, r14
0x18001b788  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b78d  test    byte ptr [rdi], 2
0x18001b790  jnz     short loc_18001B7B9
0x18001b792  mov     eax, [rdi]
0x18001b794  xor     eax, esi
0x18001b796  and     eax, ebx
0x18001b798  xor     eax, [rdi]
0x18001b79a  mov     ecx, eax
0x18001b79c  xor     ecx, esi
0x18001b79e  and     ecx, r12d
0x18001b7a1  xor     ecx, eax
0x18001b7a3  mov     edx, ecx
0x18001b7a5  xor     edx, esi
0x18001b7a7  and     edx, 1
0x18001b7aa  xor     edx, ecx
0x18001b7ac  mov     eax, edx
0x18001b7ae  xor     eax, esi
0x18001b7b0  and     eax, 800h
0x18001b7b5  xor     eax, edx
0x18001b7b7  mov     [rdi], eax
0x18001b7b9  mov     rax, rdi
0x18001b7bc  add     rsp, 28h
0x18001b7c0  pop     r14
0x18001b7c2  pop     r12
0x18001b7c4  pop     rdi
0x18001b7c5  pop     rsi
0x18001b7c6  pop     rbp
0x18001b7c7  pop     rbx
0x18001b7c8  retn
```
