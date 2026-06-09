# wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2>::GetCachedFeatureEnabledState(void)

- ea: `0x18002d2e0`
- end: `0x18002d4d6`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e0d0`

## callees

- `0x18001e1d0`
- `0x1800239b0`
- `0x180028210`
- `0x18002d2e0`
- `0x18002dea0`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site_BugFixes2>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // r14d
  __int64 (__fastcall *v5)(__int64, __int64, int *); // rax
  int v6; // eax
  unsigned int v7; // r8d
  __int16 v8; // bx
  __int16 v9; // ax
  __int16 v10; // bx
  char v11; // bp
  char IsEnabled; // al
  __int16 v13; // ax
  unsigned __int16 v14; // bx
  signed __int32 v15; // eax
  bool v16; // zf
  signed __int32 v17; // r8d
  int v18; // edx
  int v19; // r9d
  signed __int32 v20; // ecx
  int v21; // ecx
  int v23; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_IPSec_Point_To_Site_BugFixes2__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_IPSec_Point_To_Site_BugFixes2__descriptor;
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
  v6 = v5(60917977, 3, &v23);
  v7 = v6 & 0xFFFFFF3F;
  v8 = 8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3)))));
  if ( (v6 & 0xFFFFFF3F) == 0 )
  {
LABEL_9:
    v9 = 0;
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl'::`2'::impl);
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
  v14 = v13 | v10;
  v15 = *(_DWORD *)a2;
  do
  {
    v16 = v23 == 0;
    v17 = v15;
    *(_DWORD *)a2 = v15;
    if ( v16 || (v15 & 2) != 0 )
    {
      v18 = v15;
    }
    else
    {
      v18 = v15
          ^ ((unsigned __int16)v15
           ^ v14)
          & 0x180
          ^ ((unsigned __int8)v14
           ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80))
          & 0x40
          ^ ((unsigned __int8)v14
           ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
          & 1
          ^ (v14
           ^ (unsigned __int16)(v15
                              ^ (v15
                               ^ v14)
                              & 0x180
                              ^ ((unsigned __int8)v14
                               ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80))
                              & 0x40
                              ^ ((unsigned __int8)v14
                               ^ (unsigned __int8)(v15 ^ (v15 ^ v14) & 0x80 ^ (v14 ^ v15 ^ (v15 ^ v14) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v18;
    }
    v19 = v15 & 4;
    if ( (v15 & 4) != 0 )
    {
      v20 = v18;
    }
    else
    {
      v20 = v18 ^ ((unsigned __int16)v18 ^ v14) & 0x400 | 4;
      *(_DWORD *)a2 = v20;
    }
    v15 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_IPSec_Point_To_Site_BugFixes2__descriptor,
            v20,
            v15);
  }
  while ( v17 != v15 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_IPSec_Point_To_Site_BugFixes2__descriptor,
      3u,
      v4);
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v21 = *(_DWORD *)a2
        ^ (v14
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v14
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v14 ^ *(_DWORD *)a2) & 0x80))
        & 0x40;
    *(_DWORD *)a2 = v21
                  ^ ((unsigned __int8)v14
                   ^ (unsigned __int8)v21)
                  & 1
                  ^ (v14
                   ^ (unsigned __int16)(v21 ^ ((unsigned __int8)v14 ^ (unsigned __int8)v21) & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18002d2e0  push    rsi
0x18002d2e2  push    rdi
0x18002d2e3  sub     rsp, 38h
0x18002d2e7  mov     rax, cs:__security_cookie
0x18002d2ee  xor     rax, rsp
0x18002d2f1  mov     [rsp+48h+var_20], rax
0x18002d2f6  mov     rsi, cs:Feature_IPSec_Point_To_Site_BugFixes2__descriptor
0x18002d2fd  mov     rdi, rdx
0x18002d300  mov     qword ptr [rdx], 0
0x18002d307  mov     eax, [rsi]
0x18002d309  mov     [rdx], eax
0x18002d30b  and     eax, 6
0x18002d30e  cmp     al, 6
0x18002d310  jz      loc_18002D4D1
0x18002d316  mov     [rsp+48h+arg_0], rbx
0x18002d31b  mov     [rsp+48h+var_18], r14
0x18002d320  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002d325  mov     r14d, eax
0x18002d328  mov     [rsp+48h+var_28], 0
0x18002d330  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18002d337  test    rax, rax
0x18002d33a  jnz     short loc_18002D348
0x18002d33c  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002d343  test    rax, rax
0x18002d346  jz      short loc_18002D39D
0x18002d348  lea     r8, [rsp+48h+var_28]
0x18002d34d  mov     edx, 3
0x18002d352  mov     ecx, 3A188D9h
0x18002d357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d35c  mov     r8d, eax
0x18002d35f  mov     edx, eax
0x18002d361  and     r8d, 0FFFFFF3Fh
0x18002d368  and     eax, 40h
0x18002d36b  and     edx, 80h
0x18002d371  mov     ecx, r8d
0x18002d374  and     ecx, 3
0x18002d377  shl     ecx, 2
0x18002d37a  or      ecx, eax
0x18002d37c  shl     ecx, 2
0x18002d37f  or      ecx, edx
0x18002d381  lea     ebx, ds:0[rcx*8]
0x18002d388  test    r8d, r8d
0x18002d38b  jz      short loc_18002D39F
0x18002d38d  xor     eax, eax
0x18002d38f  mov     ecx, 40h ; '@'
0x18002d394  cmp     r8d, 2
0x18002d398  cmovz   eax, ecx
0x18002d39b  jmp     short loc_18002D3A1
0x18002d39d  xor     ebx, ebx
0x18002d39f  xor     eax, eax
0x18002d3a1  or      ebx, eax
0x18002d3a3  mov     [rsp+48h+arg_10], rbp
0x18002d3a8  mov     eax, ebx
0x18002d3aa  and     eax, 0C00h
0x18002d3af  cmp     eax, 0C00h
0x18002d3b4  jnz     short loc_18002D3BB
0x18002d3b6  mov     bpl, 1
0x18002d3b9  jmp     short loc_18002D3C3
0x18002d3bb  xor     bpl, bpl
0x18002d3be  test    bl, 40h
0x18002d3c1  jz      short loc_18002D3DE
0x18002d3c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site> `wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl(void)'::`2'::impl
0x18002d3ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(wil::ReportingKind)
0x18002d3cf  test    bpl, bpl
0x18002d3d2  jz      short loc_18002D3E0
0x18002d3d4  test    al, al
0x18002d3d6  jnz     short loc_18002D3E0
0x18002d3d8  btr     ebx, 0Ah
0x18002d3dc  jmp     short loc_18002D3E0
0x18002d3de  xor     al, al
0x18002d3e0  mov     rbp, [rsp+48h+arg_10]
0x18002d3e5  test    bl, 40h
0x18002d3e8  jz      short loc_18002D3F5
0x18002d3ea  test    al, al
0x18002d3ec  jz      short loc_18002D3F5
0x18002d3ee  mov     eax, 1
0x18002d3f3  jmp     short loc_18002D3F7
0x18002d3f5  xor     eax, eax
0x18002d3f7  or      ebx, eax
0x18002d3f9  mov     eax, [rdi]
0x18002d3fb  cmp     [rsp+48h+var_28], 0
0x18002d400  mov     r8d, eax
0x18002d403  mov     [rdi], eax
0x18002d405  jz      short loc_18002D43F
0x18002d407  test    r8b, 2
0x18002d40b  jnz     short loc_18002D43F
0x18002d40d  mov     eax, ebx
0x18002d40f  xor     eax, r8d
0x18002d412  and     eax, 180h
0x18002d417  xor     eax, r8d
0x18002d41a  mov     ecx, eax
0x18002d41c  xor     ecx, ebx
0x18002d41e  and     ecx, 40h
0x18002d421  xor     ecx, eax
0x18002d423  mov     eax, ecx
0x18002d425  xor     eax, ebx
0x18002d427  and     eax, 1
0x18002d42a  xor     eax, ecx
0x18002d42c  mov     edx, eax
0x18002d42e  xor     edx, ebx
0x18002d430  and     edx, 800h
0x18002d436  xor     edx, eax
0x18002d438  or      edx, 2
0x18002d43b  mov     [rdi], edx
0x18002d43d  jmp     short loc_18002D442
0x18002d43f  mov     edx, r8d
0x18002d442  mov     r9d, r8d
0x18002d445  and     r9d, 4
0x18002d449  jnz     short loc_18002D45E
0x18002d44b  mov     ecx, ebx
0x18002d44d  xor     ecx, edx
0x18002d44f  and     ecx, 400h
0x18002d455  xor     ecx, edx
0x18002d457  or      ecx, 4
0x18002d45a  mov     [rdi], ecx
0x18002d45c  jmp     short loc_18002D460
0x18002d45e  mov     ecx, edx
0x18002d460  mov     eax, r8d
0x18002d463  lock cmpxchg [rsi], ecx
0x18002d467  jnz     short loc_18002D3FB
0x18002d469  test    r9d, r9d
0x18002d46c  jnz     short loc_18002D47E
0x18002d46e  mov     r8d, r14d
0x18002d471  mov     edx, 3
0x18002d476  mov     rcx, rsi
0x18002d479  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002d47e  mov     ecx, [rdi]
0x18002d480  mov     r14, [rsp+48h+var_18]
0x18002d485  test    cl, 2
0x18002d488  jnz     short loc_18002D4B5
0x18002d48a  mov     eax, ecx
0x18002d48c  xor     eax, ebx
0x18002d48e  and     eax, 180h
0x18002d493  xor     eax, ecx
0x18002d495  mov     ecx, eax
0x18002d497  xor     ecx, ebx
0x18002d499  and     ecx, 40h
0x18002d49c  xor     ecx, eax
0x18002d49e  mov     edx, ecx
0x18002d4a0  xor     edx, ebx
0x18002d4a2  and     edx, 1
0x18002d4a5  xor     edx, ecx
0x18002d4a7  mov     ecx, edx
0x18002d4a9  xor     ecx, ebx
0x18002d4ab  and     ecx, 800h
0x18002d4b1  xor     ecx, edx
0x18002d4b3  mov     [rdi], ecx
0x18002d4b5  mov     rbx, [rsp+48h+arg_0]
0x18002d4ba  mov     rax, rdi
0x18002d4bd  mov     rcx, [rsp+48h+var_20]
0x18002d4c2  xor     rcx, rsp; StackCookie
0x18002d4c5  call    __security_check_cookie
0x18002d4ca  add     rsp, 38h
0x18002d4ce  pop     rdi
0x18002d4cf  pop     rsi
0x18002d4d0  retn
0x18002d4d1  mov     rax, rdi
0x18002d4d4  jmp     short loc_18002D4BD
```
