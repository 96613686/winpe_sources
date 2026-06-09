# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(void)

- ea: `0x1800124a8`
- end: `0x180012675`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001363c`

## callees

- `0x180005c18`
- `0x180009714`
- `0x1800124a8`
- `0x1800138b0`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFix_44936384__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(44936384, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFix_44936384__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFix_44936384__descriptor, 3, v4);
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
0x1800124a8  mov     [rsp+arg_0], rcx
0x1800124ad  push    rbx
0x1800124ae  push    rbp
0x1800124af  push    rsi
0x1800124b0  push    rdi
0x1800124b1  push    r12
0x1800124b3  push    r14
0x1800124b5  sub     rsp, 28h
0x1800124b9  mov     r14, cs:Feature_BugFix_44936384__descriptor
0x1800124c0  mov     rdi, rdx
0x1800124c3  mov     qword ptr [rdx], 0
0x1800124ca  mov     eax, [r14]
0x1800124cd  mov     [rdx], eax
0x1800124cf  and     eax, 6
0x1800124d2  cmp     al, 6
0x1800124d4  jz      loc_180012665
0x1800124da  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800124df  mov     ebp, eax
0x1800124e1  mov     dword ptr [rsp+58h+arg_0], 0
0x1800124e9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800124f0  test    rax, rax
0x1800124f3  jz      short loc_18001250D
0x1800124f5  lea     r8, [rsp+58h+arg_0]
0x1800124fa  mov     edx, 3
0x1800124ff  mov     ecx, 2ADACC0h
0x180012504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012509  mov     edx, eax
0x18001250b  jmp     short loc_18001251B
0x18001250d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012514  test    rax, rax
0x180012517  jnz     short loc_1800124F5
0x180012519  xor     edx, edx
0x18001251b  mov     r8d, edx
0x18001251e  mov     eax, edx
0x180012520  and     r8d, 0FFFFFF3Fh
0x180012527  and     edx, 80h
0x18001252d  mov     ecx, r8d
0x180012530  mov     r12d, 40h ; '@'
0x180012536  and     ecx, 3
0x180012539  and     eax, r12d
0x18001253c  shl     ecx, 2
0x18001253f  or      ecx, eax
0x180012541  shl     ecx, 2
0x180012544  or      ecx, edx
0x180012546  lea     ebx, ds:0[rcx*8]
0x18001254d  test    r8d, r8d
0x180012550  jnz     short loc_180012557
0x180012552  mov     eax, r12d
0x180012555  jmp     short loc_180012561
0x180012557  xor     eax, eax
0x180012559  cmp     r8d, 2
0x18001255d  cmovz   eax, r12d
0x180012561  or      ebx, eax
0x180012563  mov     ecx, 0C00h
0x180012568  mov     eax, ebx
0x18001256a  and     eax, ecx
0x18001256c  cmp     eax, ecx
0x18001256e  jnz     short loc_180012575
0x180012570  mov     sil, 1
0x180012573  jmp     short loc_18001257D
0x180012575  xor     sil, sil
0x180012578  test    r12b, bl
0x18001257b  jz      short loc_180012598
0x18001257d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x180012584  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x180012589  test    sil, sil
0x18001258c  jz      short loc_18001259A
0x18001258e  test    al, al
0x180012590  jnz     short loc_18001259A
0x180012592  btr     ebx, 0Ah
0x180012596  jmp     short loc_18001259A
0x180012598  xor     al, al
0x18001259a  test    r12b, bl
0x18001259d  jz      short loc_1800125AA
0x18001259f  test    al, al
0x1800125a1  jz      short loc_1800125AA
0x1800125a3  mov     esi, 1
0x1800125a8  jmp     short loc_1800125AC
0x1800125aa  xor     esi, esi
0x1800125ac  mov     eax, [rdi]
0x1800125ae  or      esi, ebx
0x1800125b0  mov     ebx, 180h
0x1800125b5  cmp     dword ptr [rsp+58h+arg_0], 0
0x1800125ba  mov     edx, eax
0x1800125bc  mov     [rdi], eax
0x1800125be  jz      short loc_1800125F8
0x1800125c0  test    dl, 2
0x1800125c3  jnz     short loc_1800125F8
0x1800125c5  mov     eax, esi
0x1800125c7  xor     eax, edx
0x1800125c9  and     eax, ebx
0x1800125cb  xor     eax, edx
0x1800125cd  mov     ecx, eax
0x1800125cf  xor     ecx, esi
0x1800125d1  and     ecx, r12d
0x1800125d4  xor     ecx, eax
0x1800125d6  mov     eax, ecx
0x1800125d8  xor     eax, esi
0x1800125da  and     eax, 1
0x1800125dd  xor     eax, ecx
0x1800125df  mov     r8d, eax
0x1800125e2  xor     r8d, esi
0x1800125e5  and     r8d, 800h
0x1800125ec  xor     r8d, eax
0x1800125ef  or      r8d, 2
0x1800125f3  mov     [rdi], r8d
0x1800125f6  jmp     short loc_1800125FB
0x1800125f8  mov     r8d, edx
0x1800125fb  mov     r9d, edx
0x1800125fe  and     r9d, 4
0x180012602  jnz     short loc_180012619
0x180012604  mov     ecx, esi
0x180012606  xor     ecx, r8d
0x180012609  and     ecx, 400h
0x18001260f  xor     ecx, r8d
0x180012612  or      ecx, 4
0x180012615  mov     [rdi], ecx
0x180012617  jmp     short loc_18001261C
0x180012619  mov     ecx, r8d
0x18001261c  mov     eax, edx
0x18001261e  lock cmpxchg [r14], ecx
0x180012623  jnz     short loc_1800125B5
0x180012625  test    r9d, r9d
0x180012628  jnz     short loc_180012639
0x18001262a  mov     r8d, ebp
0x18001262d  lea     edx, [r9+3]
0x180012631  mov     rcx, r14
0x180012634  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012639  test    byte ptr [rdi], 2
0x18001263c  jnz     short loc_180012665
0x18001263e  mov     eax, [rdi]
0x180012640  xor     eax, esi
0x180012642  and     eax, ebx
0x180012644  xor     eax, [rdi]
0x180012646  mov     ecx, eax
0x180012648  xor     ecx, esi
0x18001264a  and     ecx, r12d
0x18001264d  xor     ecx, eax
0x18001264f  mov     edx, ecx
0x180012651  xor     edx, esi
0x180012653  and     edx, 1
0x180012656  xor     edx, ecx
0x180012658  mov     eax, edx
0x18001265a  xor     eax, esi
0x18001265c  and     eax, 800h
0x180012661  xor     eax, edx
0x180012663  mov     [rdi], eax
0x180012665  mov     rax, rdi
0x180012668  add     rsp, 28h
0x18001266c  pop     r14
0x18001266e  pop     r12
0x180012670  pop     rdi
0x180012671  pop     rsi
0x180012672  pop     rbp
0x180012673  pop     rbx
0x180012674  retn
```
