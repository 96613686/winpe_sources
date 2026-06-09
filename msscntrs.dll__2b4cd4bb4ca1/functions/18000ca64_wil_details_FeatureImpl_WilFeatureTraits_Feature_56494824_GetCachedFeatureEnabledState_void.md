# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ca64`
- end: `0x18000cc2c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `456`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001085c`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000ca64`
- `0x180010998`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_56494824__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56494824__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56494824, 3, &v20);
  }
  else
  {
    v6 = 0;
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_11:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_15;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_11;
  IsEnabled = 0;
LABEL_15:
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56494824__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_56494824__descriptor, 3, v4);
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
0x18000ca64  mov     [rsp+arg_0], rcx
0x18000ca69  push    rbx
0x18000ca6a  push    rbp
0x18000ca6b  push    rsi
0x18000ca6c  push    rdi
0x18000ca6d  push    r12
0x18000ca6f  push    r14
0x18000ca71  sub     rsp, 28h
0x18000ca75  mov     r14, cs:Feature_56494824__descriptor
0x18000ca7c  mov     rdi, rdx
0x18000ca7f  mov     qword ptr [rdx], 0
0x18000ca86  mov     eax, [r14]
0x18000ca89  mov     [rdx], eax
0x18000ca8b  and     eax, 6
0x18000ca8e  cmp     al, 6
0x18000ca90  jz      loc_18000CC1C
0x18000ca96  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ca9b  mov     ebp, eax
0x18000ca9d  mov     dword ptr [rsp+58h+arg_0], 0
0x18000caa5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000caac  test    rax, rax
0x18000caaf  jz      short loc_18000CAC9
0x18000cab1  lea     r8, [rsp+58h+arg_0]
0x18000cab6  mov     edx, 3
0x18000cabb  mov     ecx, 35E0AE8h
0x18000cac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cac5  mov     edx, eax
0x18000cac7  jmp     short loc_18000CAD7
0x18000cac9  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000cad0  test    rax, rax
0x18000cad3  jnz     short loc_18000CAB1
0x18000cad5  xor     edx, edx
0x18000cad7  mov     r8d, edx
0x18000cada  mov     eax, edx
0x18000cadc  and     r8d, 0FFFFFF3Fh
0x18000cae3  and     edx, 80h
0x18000cae9  mov     ecx, r8d
0x18000caec  mov     r12d, 40h ; '@'
0x18000caf2  and     ecx, 3
0x18000caf5  and     eax, r12d
0x18000caf8  shl     ecx, 2
0x18000cafb  or      ecx, eax
0x18000cafd  xor     eax, eax
0x18000caff  shl     ecx, 2
0x18000cb02  or      ecx, edx
0x18000cb04  lea     ebx, ds:0[rcx*8]
0x18000cb0b  test    r8d, r8d
0x18000cb0e  jz      short loc_18000CB18
0x18000cb10  cmp     r8d, 2
0x18000cb14  cmovz   eax, r12d
0x18000cb18  or      ebx, eax
0x18000cb1a  mov     ecx, 0C00h
0x18000cb1f  mov     eax, ebx
0x18000cb21  and     eax, ecx
0x18000cb23  cmp     eax, ecx
0x18000cb25  jnz     short loc_18000CB2C
0x18000cb27  mov     sil, 1
0x18000cb2a  jmp     short loc_18000CB34
0x18000cb2c  xor     sil, sil
0x18000cb2f  test    r12b, bl
0x18000cb32  jz      short loc_18000CB4F
0x18000cb34  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000cb3b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000cb40  test    sil, sil
0x18000cb43  jz      short loc_18000CB51
0x18000cb45  test    al, al
0x18000cb47  jnz     short loc_18000CB51
0x18000cb49  btr     ebx, 0Ah
0x18000cb4d  jmp     short loc_18000CB51
0x18000cb4f  xor     al, al
0x18000cb51  test    r12b, bl
0x18000cb54  jz      short loc_18000CB61
0x18000cb56  test    al, al
0x18000cb58  jz      short loc_18000CB61
0x18000cb5a  mov     esi, 1
0x18000cb5f  jmp     short loc_18000CB63
0x18000cb61  xor     esi, esi
0x18000cb63  mov     eax, [rdi]
0x18000cb65  or      esi, ebx
0x18000cb67  mov     ebx, 180h
0x18000cb6c  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000cb71  mov     edx, eax
0x18000cb73  mov     [rdi], eax
0x18000cb75  jz      short loc_18000CBAF
0x18000cb77  test    dl, 2
0x18000cb7a  jnz     short loc_18000CBAF
0x18000cb7c  mov     eax, esi
0x18000cb7e  xor     eax, edx
0x18000cb80  and     eax, ebx
0x18000cb82  xor     eax, edx
0x18000cb84  mov     ecx, eax
0x18000cb86  xor     ecx, esi
0x18000cb88  and     ecx, r12d
0x18000cb8b  xor     ecx, eax
0x18000cb8d  mov     eax, ecx
0x18000cb8f  xor     eax, esi
0x18000cb91  and     eax, 1
0x18000cb94  xor     eax, ecx
0x18000cb96  mov     r8d, eax
0x18000cb99  xor     r8d, esi
0x18000cb9c  and     r8d, 800h
0x18000cba3  xor     r8d, eax
0x18000cba6  or      r8d, 2
0x18000cbaa  mov     [rdi], r8d
0x18000cbad  jmp     short loc_18000CBB2
0x18000cbaf  mov     r8d, edx
0x18000cbb2  mov     r9d, edx
0x18000cbb5  and     r9d, 4
0x18000cbb9  jnz     short loc_18000CBD0
0x18000cbbb  mov     ecx, esi
0x18000cbbd  xor     ecx, r8d
0x18000cbc0  and     ecx, 400h
0x18000cbc6  xor     ecx, r8d
0x18000cbc9  or      ecx, 4
0x18000cbcc  mov     [rdi], ecx
0x18000cbce  jmp     short loc_18000CBD3
0x18000cbd0  mov     ecx, r8d
0x18000cbd3  mov     eax, edx
0x18000cbd5  lock cmpxchg [r14], ecx
0x18000cbda  jnz     short loc_18000CB6C
0x18000cbdc  test    r9d, r9d
0x18000cbdf  jnz     short loc_18000CBF0
0x18000cbe1  mov     r8d, ebp
0x18000cbe4  lea     edx, [r9+3]
0x18000cbe8  mov     rcx, r14
0x18000cbeb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000cbf0  test    byte ptr [rdi], 2
0x18000cbf3  jnz     short loc_18000CC1C
0x18000cbf5  mov     eax, [rdi]
0x18000cbf7  xor     eax, esi
0x18000cbf9  and     eax, ebx
0x18000cbfb  xor     eax, [rdi]
0x18000cbfd  mov     ecx, eax
0x18000cbff  xor     ecx, esi
0x18000cc01  and     ecx, r12d
0x18000cc04  xor     ecx, eax
0x18000cc06  mov     edx, ecx
0x18000cc08  xor     edx, esi
0x18000cc0a  and     edx, 1
0x18000cc0d  xor     edx, ecx
0x18000cc0f  mov     eax, edx
0x18000cc11  xor     eax, esi
0x18000cc13  and     eax, 800h
0x18000cc18  xor     eax, edx
0x18000cc1a  mov     [rdi], eax
0x18000cc1c  mov     rax, rdi
0x18000cc1f  add     rsp, 28h
0x18000cc23  pop     r14
0x18000cc25  pop     r12
0x18000cc27  pop     rdi
0x18000cc28  pop     rsi
0x18000cc29  pop     rbp
0x18000cc2a  pop     rbx
0x18000cc2b  retn
```
