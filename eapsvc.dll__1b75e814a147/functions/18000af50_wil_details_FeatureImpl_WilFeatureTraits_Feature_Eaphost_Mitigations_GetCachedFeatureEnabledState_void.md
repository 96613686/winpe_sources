# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_Mitigations>::GetCachedFeatureEnabledState(void)

- ea: `0x18000af50`
- end: `0x18000b11d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Eaphost_Mitigations@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be20`

## callees

- `0x180004f18`
- `0x180008dc0`
- `0x18000af50`
- `0x18000bec0`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_Mitigations>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Eaphost_Mitigations__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Eaphost_Mitigations__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58636806, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Eaphost_Mitigations__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Eaphost_Mitigations__descriptor, 3, v4);
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
0x18000af50  mov     [rsp+arg_0], rcx
0x18000af55  push    rbx
0x18000af56  push    rbp
0x18000af57  push    rsi
0x18000af58  push    rdi
0x18000af59  push    r12
0x18000af5b  push    r14
0x18000af5d  sub     rsp, 28h
0x18000af61  mov     r14, cs:Feature_Eaphost_Mitigations__descriptor
0x18000af68  mov     rdi, rdx
0x18000af6b  mov     qword ptr [rdx], 0
0x18000af72  mov     eax, [r14]
0x18000af75  mov     [rdx], eax
0x18000af77  and     eax, 6
0x18000af7a  cmp     al, 6
0x18000af7c  jz      loc_18000B10D
0x18000af82  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000af87  mov     ebp, eax
0x18000af89  mov     dword ptr [rsp+58h+arg_0], 0
0x18000af91  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000af98  test    rax, rax
0x18000af9b  jz      short loc_18000AFB5
0x18000af9d  lea     r8, [rsp+58h+arg_0]
0x18000afa2  mov     edx, 3
0x18000afa7  mov     ecx, 37EBA06h
0x18000afac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb1  mov     edx, eax
0x18000afb3  jmp     short loc_18000AFC3
0x18000afb5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000afbc  test    rax, rax
0x18000afbf  jnz     short loc_18000AF9D
0x18000afc1  xor     edx, edx
0x18000afc3  mov     r8d, edx
0x18000afc6  mov     eax, edx
0x18000afc8  and     r8d, 0FFFFFF3Fh
0x18000afcf  and     edx, 80h
0x18000afd5  mov     ecx, r8d
0x18000afd8  mov     r12d, 40h ; '@'
0x18000afde  and     ecx, 3
0x18000afe1  and     eax, r12d
0x18000afe4  shl     ecx, 2
0x18000afe7  or      ecx, eax
0x18000afe9  shl     ecx, 2
0x18000afec  or      ecx, edx
0x18000afee  lea     ebx, ds:0[rcx*8]
0x18000aff5  test    r8d, r8d
0x18000aff8  jnz     short loc_18000AFFF
0x18000affa  mov     eax, r12d
0x18000affd  jmp     short loc_18000B009
0x18000afff  xor     eax, eax
0x18000b001  cmp     r8d, 2
0x18000b005  cmovz   eax, r12d
0x18000b009  or      ebx, eax
0x18000b00b  mov     ecx, 0C00h
0x18000b010  mov     eax, ebx
0x18000b012  and     eax, ecx
0x18000b014  cmp     eax, ecx
0x18000b016  jnz     short loc_18000B01D
0x18000b018  mov     sil, 1
0x18000b01b  jmp     short loc_18000B025
0x18000b01d  xor     sil, sil
0x18000b020  test    r12b, bl
0x18000b023  jz      short loc_18000B040
0x18000b025  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000b02c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000b031  test    sil, sil
0x18000b034  jz      short loc_18000B042
0x18000b036  test    al, al
0x18000b038  jnz     short loc_18000B042
0x18000b03a  btr     ebx, 0Ah
0x18000b03e  jmp     short loc_18000B042
0x18000b040  xor     al, al
0x18000b042  test    r12b, bl
0x18000b045  jz      short loc_18000B052
0x18000b047  test    al, al
0x18000b049  jz      short loc_18000B052
0x18000b04b  mov     esi, 1
0x18000b050  jmp     short loc_18000B054
0x18000b052  xor     esi, esi
0x18000b054  mov     eax, [rdi]
0x18000b056  or      esi, ebx
0x18000b058  mov     ebx, 180h
0x18000b05d  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000b062  mov     edx, eax
0x18000b064  mov     [rdi], eax
0x18000b066  jz      short loc_18000B0A0
0x18000b068  test    dl, 2
0x18000b06b  jnz     short loc_18000B0A0
0x18000b06d  mov     eax, esi
0x18000b06f  xor     eax, edx
0x18000b071  and     eax, ebx
0x18000b073  xor     eax, edx
0x18000b075  mov     ecx, eax
0x18000b077  xor     ecx, esi
0x18000b079  and     ecx, r12d
0x18000b07c  xor     ecx, eax
0x18000b07e  mov     eax, ecx
0x18000b080  xor     eax, esi
0x18000b082  and     eax, 1
0x18000b085  xor     eax, ecx
0x18000b087  mov     r8d, eax
0x18000b08a  xor     r8d, esi
0x18000b08d  and     r8d, 800h
0x18000b094  xor     r8d, eax
0x18000b097  or      r8d, 2
0x18000b09b  mov     [rdi], r8d
0x18000b09e  jmp     short loc_18000B0A3
0x18000b0a0  mov     r8d, edx
0x18000b0a3  mov     r9d, edx
0x18000b0a6  and     r9d, 4
0x18000b0aa  jnz     short loc_18000B0C1
0x18000b0ac  mov     ecx, esi
0x18000b0ae  xor     ecx, r8d
0x18000b0b1  and     ecx, 400h
0x18000b0b7  xor     ecx, r8d
0x18000b0ba  or      ecx, 4
0x18000b0bd  mov     [rdi], ecx
0x18000b0bf  jmp     short loc_18000B0C4
0x18000b0c1  mov     ecx, r8d
0x18000b0c4  mov     eax, edx
0x18000b0c6  lock cmpxchg [r14], ecx
0x18000b0cb  jnz     short loc_18000B05D
0x18000b0cd  test    r9d, r9d
0x18000b0d0  jnz     short loc_18000B0E1
0x18000b0d2  mov     r8d, ebp
0x18000b0d5  lea     edx, [r9+3]
0x18000b0d9  mov     rcx, r14
0x18000b0dc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b0e1  test    byte ptr [rdi], 2
0x18000b0e4  jnz     short loc_18000B10D
0x18000b0e6  mov     eax, [rdi]
0x18000b0e8  xor     eax, esi
0x18000b0ea  and     eax, ebx
0x18000b0ec  xor     eax, [rdi]
0x18000b0ee  mov     ecx, eax
0x18000b0f0  xor     ecx, esi
0x18000b0f2  and     ecx, r12d
0x18000b0f5  xor     ecx, eax
0x18000b0f7  mov     edx, ecx
0x18000b0f9  xor     edx, esi
0x18000b0fb  and     edx, 1
0x18000b0fe  xor     edx, ecx
0x18000b100  mov     eax, edx
0x18000b102  xor     eax, esi
0x18000b104  and     eax, 800h
0x18000b109  xor     eax, edx
0x18000b10b  mov     [rdi], eax
0x18000b10d  mov     rax, rdi
0x18000b110  add     rsp, 28h
0x18000b114  pop     r14
0x18000b116  pop     r12
0x18000b118  pop     rdi
0x18000b119  pop     rsi
0x18000b11a  pop     rbp
0x18000b11b  pop     rbx
0x18000b11c  retn
```
