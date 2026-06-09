# wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_Rule_Validation>::GetCachedFeatureEnabledState(void)

- ea: `0x18002d0d0`
- end: `0x18002d2cc`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_Rule_Validation@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e010`

## callees

- `0x18001e1d0`
- `0x1800239b0`
- `0x180028210`
- `0x18002d0d0`
- `0x18002e180`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFix_Rule_Validation>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, int *); // rax
  int v6; // eax
  unsigned int v7; // r8d
  __int16 v8; // bx
  __int16 v9; // ax
  __int16 v10; // bx
  char v11; // si
  char IsEnabled; // al
  __int16 v13; // si
  signed __int32 v14; // eax
  unsigned __int16 v15; // si
  bool v16; // zf
  signed __int32 v17; // r8d
  int v18; // edx
  int v19; // r9d
  signed __int32 v20; // ecx
  int v21; // ecx
  int v23; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_IPSec_Point_To_Site_BugFix_Rule_Validation__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_IPSec_Point_To_Site_BugFix_Rule_Validation__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v23 = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      v8 = 0;
      goto LABEL_9;
    }
  }
  v6 = v5(61502651, 3, &v23);
  v7 = v6 & 0xFFFFFF3F;
  v8 = 8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3)))));
  if ( (v6 & 0xFFFFFF3F) == 0 )
  {
LABEL_9:
    v9 = 64;
    goto LABEL_10;
  }
  v9 = 0;
  if ( v7 == 2 )
    v9 = 64;
LABEL_10:
  v10 = v9 | v8;
  if ( (v10 & 0xC00) == 0xC00 )
  {
    v11 = 1;
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3>::GetImpl'::`2'::impl);
    if ( v11 && !IsEnabled )
      v10 &= ~0x400u;
    goto LABEL_17;
  }
  v11 = 0;
  if ( (v10 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v13 = (v10 & 0x40) != 0 && IsEnabled;
  v14 = *(_DWORD *)a2;
  v15 = v10 | v13;
  do
  {
    v16 = v23 == 0;
    v17 = v14;
    *(_DWORD *)a2 = v14;
    if ( v16 || (v14 & 2) != 0 )
    {
      v18 = v14;
    }
    else
    {
      v18 = v14
          ^ ((unsigned __int16)v14
           ^ v15)
          & 0x180
          ^ ((unsigned __int8)v15
           ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80))
          & 0x40
          ^ ((unsigned __int8)v15
           ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80 ^ (v15 ^ v14 ^ (v14 ^ v15) & 0x80) & 0x40))
          & 1
          ^ (v15
           ^ (unsigned __int16)(v14
                              ^ (v14
                               ^ v15)
                              & 0x180
                              ^ ((unsigned __int8)v15
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80))
                              & 0x40
                              ^ ((unsigned __int8)v15
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80 ^ (v15 ^ v14 ^ (v14 ^ v15) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v18;
    }
    v19 = v14 & 4;
    if ( (v14 & 4) != 0 )
    {
      v20 = v18;
    }
    else
    {
      v20 = v18 ^ ((unsigned __int16)v18 ^ v15) & 0x400 | 4;
      *(_DWORD *)a2 = v20;
    }
    v14 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_IPSec_Point_To_Site_BugFix_Rule_Validation__descriptor,
            v20,
            v14);
  }
  while ( v17 != v14 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_IPSec_Point_To_Site_BugFix_Rule_Validation__descriptor,
      3u,
      v4);
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v21 = *(_DWORD *)a2
        ^ (v15
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v15
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v15 ^ *(_DWORD *)a2) & 0x80))
        & 0x40;
    *(_DWORD *)a2 = v21
                  ^ ((unsigned __int8)v15
                   ^ (unsigned __int8)v21)
                  & 1
                  ^ (v15
                   ^ (unsigned __int16)(v21 ^ ((unsigned __int8)v15 ^ (unsigned __int8)v21) & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18002d0d0  push    rdi
0x18002d0d2  push    r14
0x18002d0d4  sub     rsp, 38h
0x18002d0d8  mov     rax, cs:__security_cookie
0x18002d0df  xor     rax, rsp
0x18002d0e2  mov     [rsp+48h+var_20], rax
0x18002d0e7  mov     r14, cs:Feature_IPSec_Point_To_Site_BugFix_Rule_Validation__descriptor
0x18002d0ee  mov     rdi, rdx
0x18002d0f1  mov     qword ptr [rdx], 0
0x18002d0f8  mov     eax, [r14]
0x18002d0fb  mov     [rdx], eax
0x18002d0fd  and     eax, 6
0x18002d100  cmp     al, 6
0x18002d102  jz      loc_18002D2C7
0x18002d108  mov     [rsp+48h+arg_0], rbx
0x18002d10d  mov     [rsp+48h+arg_10], rbp
0x18002d112  mov     [rsp+48h+var_18], rsi
0x18002d117  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002d11c  mov     ebp, eax
0x18002d11e  mov     [rsp+48h+var_28], 0
0x18002d126  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18002d12d  test    rax, rax
0x18002d130  jnz     short loc_18002D13E
0x18002d132  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002d139  test    rax, rax
0x18002d13c  jz      short loc_18002D193
0x18002d13e  lea     r8, [rsp+48h+var_28]
0x18002d143  mov     edx, 3
0x18002d148  mov     ecx, 3AA74BBh
0x18002d14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d152  mov     r8d, eax
0x18002d155  mov     edx, eax
0x18002d157  and     r8d, 0FFFFFF3Fh
0x18002d15e  and     eax, 40h
0x18002d161  and     edx, 80h
0x18002d167  mov     ecx, r8d
0x18002d16a  and     ecx, 3
0x18002d16d  shl     ecx, 2
0x18002d170  or      ecx, eax
0x18002d172  shl     ecx, 2
0x18002d175  or      ecx, edx
0x18002d177  lea     ebx, ds:0[rcx*8]
0x18002d17e  test    r8d, r8d
0x18002d181  jz      short loc_18002D195
0x18002d183  xor     eax, eax
0x18002d185  mov     ecx, 40h ; '@'
0x18002d18a  cmp     r8d, 2
0x18002d18e  cmovz   eax, ecx
0x18002d191  jmp     short loc_18002D19A
0x18002d193  xor     ebx, ebx
0x18002d195  mov     eax, 40h ; '@'
0x18002d19a  or      ebx, eax
0x18002d19c  mov     eax, ebx
0x18002d19e  and     eax, 0C00h
0x18002d1a3  cmp     eax, 0C00h
0x18002d1a8  jnz     short loc_18002D1AF
0x18002d1aa  mov     sil, 1
0x18002d1ad  jmp     short loc_18002D1B7
0x18002d1af  xor     sil, sil
0x18002d1b2  test    bl, 40h
0x18002d1b5  jz      short loc_18002D1D2
0x18002d1b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3> `wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3>::GetImpl(void)'::`2'::impl
0x18002d1be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3>::__private_IsEnabled(wil::ReportingKind)
0x18002d1c3  test    sil, sil
0x18002d1c6  jz      short loc_18002D1D4
0x18002d1c8  test    al, al
0x18002d1ca  jnz     short loc_18002D1D4
0x18002d1cc  btr     ebx, 0Ah
0x18002d1d0  jmp     short loc_18002D1D4
0x18002d1d2  xor     al, al
0x18002d1d4  test    bl, 40h
0x18002d1d7  jz      short loc_18002D1E4
0x18002d1d9  test    al, al
0x18002d1db  jz      short loc_18002D1E4
0x18002d1dd  mov     esi, 1
0x18002d1e2  jmp     short loc_18002D1E6
0x18002d1e4  xor     esi, esi
0x18002d1e6  mov     eax, [rdi]
0x18002d1e8  or      esi, ebx
0x18002d1ea  mov     rbx, [rsp+48h+arg_0]
0x18002d1ef  cmp     [rsp+48h+var_28], 0
0x18002d1f4  mov     r8d, eax
0x18002d1f7  mov     [rdi], eax
0x18002d1f9  jz      short loc_18002D233
0x18002d1fb  test    r8b, 2
0x18002d1ff  jnz     short loc_18002D233
0x18002d201  mov     eax, esi
0x18002d203  xor     eax, r8d
0x18002d206  and     eax, 180h
0x18002d20b  xor     eax, r8d
0x18002d20e  mov     ecx, eax
0x18002d210  xor     ecx, esi
0x18002d212  and     ecx, 40h
0x18002d215  xor     ecx, eax
0x18002d217  mov     eax, ecx
0x18002d219  xor     eax, esi
0x18002d21b  and     eax, 1
0x18002d21e  xor     eax, ecx
0x18002d220  mov     edx, eax
0x18002d222  xor     edx, esi
0x18002d224  and     edx, 800h
0x18002d22a  xor     edx, eax
0x18002d22c  or      edx, 2
0x18002d22f  mov     [rdi], edx
0x18002d231  jmp     short loc_18002D236
0x18002d233  mov     edx, r8d
0x18002d236  mov     r9d, r8d
0x18002d239  and     r9d, 4
0x18002d23d  jnz     short loc_18002D252
0x18002d23f  mov     ecx, esi
0x18002d241  xor     ecx, edx
0x18002d243  and     ecx, 400h
0x18002d249  xor     ecx, edx
0x18002d24b  or      ecx, 4
0x18002d24e  mov     [rdi], ecx
0x18002d250  jmp     short loc_18002D254
0x18002d252  mov     ecx, edx
0x18002d254  mov     eax, r8d
0x18002d257  lock cmpxchg [r14], ecx
0x18002d25c  jnz     short loc_18002D1EF
0x18002d25e  test    r9d, r9d
0x18002d261  jnz     short loc_18002D273
0x18002d263  mov     r8d, ebp
0x18002d266  mov     edx, 3
0x18002d26b  mov     rcx, r14
0x18002d26e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002d273  mov     ecx, [rdi]
0x18002d275  mov     rbp, [rsp+48h+arg_10]
0x18002d27a  test    cl, 2
0x18002d27d  jnz     short loc_18002D2AA
0x18002d27f  mov     eax, ecx
0x18002d281  xor     eax, esi
0x18002d283  and     eax, 180h
0x18002d288  xor     eax, ecx
0x18002d28a  mov     ecx, eax
0x18002d28c  xor     ecx, esi
0x18002d28e  and     ecx, 40h
0x18002d291  xor     ecx, eax
0x18002d293  mov     edx, ecx
0x18002d295  xor     edx, esi
0x18002d297  and     edx, 1
0x18002d29a  xor     edx, ecx
0x18002d29c  mov     ecx, edx
0x18002d29e  xor     ecx, esi
0x18002d2a0  and     ecx, 800h
0x18002d2a6  xor     ecx, edx
0x18002d2a8  mov     [rdi], ecx
0x18002d2aa  mov     rsi, [rsp+48h+var_18]
0x18002d2af  mov     rax, rdi
0x18002d2b2  mov     rcx, [rsp+48h+var_20]
0x18002d2b7  xor     rcx, rsp; StackCookie
0x18002d2ba  call    __security_check_cookie
0x18002d2bf  add     rsp, 38h
0x18002d2c3  pop     r14
0x18002d2c5  pop     rdi
0x18002d2c6  retn
0x18002d2c7  mov     rax, rdi
0x18002d2ca  jmp     short loc_18002D2B2
```
