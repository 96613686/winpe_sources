# wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3>::GetCachedFeatureEnabledState(void)

- ea: `0x18002d4e0`
- end: `0x18002d6dc`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e180`

## callees

- `0x18001e1d0`
- `0x1800239b0`
- `0x180028210`
- `0x18002d4e0`
- `0x18002e0d0`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes3>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_IPSec_Point_To_Site_BugFixes3__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_IPSec_Point_To_Site_BugFixes3__descriptor;
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
  v6 = v5(61555960, 3, &v23);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_IPSec_Point_To_Site_BugFixes3__descriptor,
            v20,
            v14);
  }
  while ( v17 != v14 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_IPSec_Point_To_Site_BugFixes3__descriptor,
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
0x18002d4e0  push    rdi
0x18002d4e2  push    r14
0x18002d4e4  sub     rsp, 38h
0x18002d4e8  mov     rax, cs:__security_cookie
0x18002d4ef  xor     rax, rsp
0x18002d4f2  mov     [rsp+48h+var_20], rax
0x18002d4f7  mov     r14, cs:Feature_IPSec_Point_To_Site_BugFixes3__descriptor
0x18002d4fe  mov     rdi, rdx
0x18002d501  mov     qword ptr [rdx], 0
0x18002d508  mov     eax, [r14]
0x18002d50b  mov     [rdx], eax
0x18002d50d  and     eax, 6
0x18002d510  cmp     al, 6
0x18002d512  jz      loc_18002D6D7
0x18002d518  mov     [rsp+48h+arg_0], rbx
0x18002d51d  mov     [rsp+48h+arg_10], rbp
0x18002d522  mov     [rsp+48h+var_18], rsi
0x18002d527  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002d52c  mov     ebp, eax
0x18002d52e  mov     [rsp+48h+var_28], 0
0x18002d536  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18002d53d  test    rax, rax
0x18002d540  jnz     short loc_18002D54E
0x18002d542  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002d549  test    rax, rax
0x18002d54c  jz      short loc_18002D5A3
0x18002d54e  lea     r8, [rsp+48h+var_28]
0x18002d553  mov     edx, 3
0x18002d558  mov     ecx, 3AB44F8h
0x18002d55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d562  mov     r8d, eax
0x18002d565  mov     edx, eax
0x18002d567  and     r8d, 0FFFFFF3Fh
0x18002d56e  and     eax, 40h
0x18002d571  and     edx, 80h
0x18002d577  mov     ecx, r8d
0x18002d57a  and     ecx, 3
0x18002d57d  shl     ecx, 2
0x18002d580  or      ecx, eax
0x18002d582  shl     ecx, 2
0x18002d585  or      ecx, edx
0x18002d587  lea     ebx, ds:0[rcx*8]
0x18002d58e  test    r8d, r8d
0x18002d591  jz      short loc_18002D5A5
0x18002d593  xor     eax, eax
0x18002d595  mov     ecx, 40h ; '@'
0x18002d59a  cmp     r8d, 2
0x18002d59e  cmovz   eax, ecx
0x18002d5a1  jmp     short loc_18002D5AA
0x18002d5a3  xor     ebx, ebx
0x18002d5a5  mov     eax, 40h ; '@'
0x18002d5aa  or      ebx, eax
0x18002d5ac  mov     eax, ebx
0x18002d5ae  and     eax, 0C00h
0x18002d5b3  cmp     eax, 0C00h
0x18002d5b8  jnz     short loc_18002D5BF
0x18002d5ba  mov     sil, 1
0x18002d5bd  jmp     short loc_18002D5C7
0x18002d5bf  xor     sil, sil
0x18002d5c2  test    bl, 40h
0x18002d5c5  jz      short loc_18002D5E2
0x18002d5c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2> `wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2>::GetImpl(void)'::`2'::impl
0x18002d5ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2>::__private_IsEnabled(wil::ReportingKind)
0x18002d5d3  test    sil, sil
0x18002d5d6  jz      short loc_18002D5E4
0x18002d5d8  test    al, al
0x18002d5da  jnz     short loc_18002D5E4
0x18002d5dc  btr     ebx, 0Ah
0x18002d5e0  jmp     short loc_18002D5E4
0x18002d5e2  xor     al, al
0x18002d5e4  test    bl, 40h
0x18002d5e7  jz      short loc_18002D5F4
0x18002d5e9  test    al, al
0x18002d5eb  jz      short loc_18002D5F4
0x18002d5ed  mov     esi, 1
0x18002d5f2  jmp     short loc_18002D5F6
0x18002d5f4  xor     esi, esi
0x18002d5f6  mov     eax, [rdi]
0x18002d5f8  or      esi, ebx
0x18002d5fa  mov     rbx, [rsp+48h+arg_0]
0x18002d5ff  cmp     [rsp+48h+var_28], 0
0x18002d604  mov     r8d, eax
0x18002d607  mov     [rdi], eax
0x18002d609  jz      short loc_18002D643
0x18002d60b  test    r8b, 2
0x18002d60f  jnz     short loc_18002D643
0x18002d611  mov     eax, esi
0x18002d613  xor     eax, r8d
0x18002d616  and     eax, 180h
0x18002d61b  xor     eax, r8d
0x18002d61e  mov     ecx, eax
0x18002d620  xor     ecx, esi
0x18002d622  and     ecx, 40h
0x18002d625  xor     ecx, eax
0x18002d627  mov     eax, ecx
0x18002d629  xor     eax, esi
0x18002d62b  and     eax, 1
0x18002d62e  xor     eax, ecx
0x18002d630  mov     edx, eax
0x18002d632  xor     edx, esi
0x18002d634  and     edx, 800h
0x18002d63a  xor     edx, eax
0x18002d63c  or      edx, 2
0x18002d63f  mov     [rdi], edx
0x18002d641  jmp     short loc_18002D646
0x18002d643  mov     edx, r8d
0x18002d646  mov     r9d, r8d
0x18002d649  and     r9d, 4
0x18002d64d  jnz     short loc_18002D662
0x18002d64f  mov     ecx, esi
0x18002d651  xor     ecx, edx
0x18002d653  and     ecx, 400h
0x18002d659  xor     ecx, edx
0x18002d65b  or      ecx, 4
0x18002d65e  mov     [rdi], ecx
0x18002d660  jmp     short loc_18002D664
0x18002d662  mov     ecx, edx
0x18002d664  mov     eax, r8d
0x18002d667  lock cmpxchg [r14], ecx
0x18002d66c  jnz     short loc_18002D5FF
0x18002d66e  test    r9d, r9d
0x18002d671  jnz     short loc_18002D683
0x18002d673  mov     r8d, ebp
0x18002d676  mov     edx, 3
0x18002d67b  mov     rcx, r14
0x18002d67e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002d683  mov     ecx, [rdi]
0x18002d685  mov     rbp, [rsp+48h+arg_10]
0x18002d68a  test    cl, 2
0x18002d68d  jnz     short loc_18002D6BA
0x18002d68f  mov     eax, ecx
0x18002d691  xor     eax, esi
0x18002d693  and     eax, 180h
0x18002d698  xor     eax, ecx
0x18002d69a  mov     ecx, eax
0x18002d69c  xor     ecx, esi
0x18002d69e  and     ecx, 40h
0x18002d6a1  xor     ecx, eax
0x18002d6a3  mov     edx, ecx
0x18002d6a5  xor     edx, esi
0x18002d6a7  and     edx, 1
0x18002d6aa  xor     edx, ecx
0x18002d6ac  mov     ecx, edx
0x18002d6ae  xor     ecx, esi
0x18002d6b0  and     ecx, 800h
0x18002d6b6  xor     ecx, edx
0x18002d6b8  mov     [rdi], ecx
0x18002d6ba  mov     rsi, [rsp+48h+var_18]
0x18002d6bf  mov     rax, rdi
0x18002d6c2  mov     rcx, [rsp+48h+var_20]
0x18002d6c7  xor     rcx, rsp; StackCookie
0x18002d6ca  call    __security_check_cookie
0x18002d6cf  add     rsp, 38h
0x18002d6d3  pop     r14
0x18002d6d5  pop     rdi
0x18002d6d6  retn
0x18002d6d7  mov     rax, rdi
0x18002d6da  jmp     short loc_18002D6C2
```
