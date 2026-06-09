# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ESIM_POLICY_MANAGER>::GetCachedFeatureEnabledState(void)

- ea: `0x140034280`
- end: `0x14003443b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ESIM_POLICY_MANAGER@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `443`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140034768`
- `0x1400349dc`

## callees

- `0x14000f648`
- `0x1400130d4`
- `0x140034280`
- `0x14003e010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ESIM_POLICY_MANAGER>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ESIM_POLICY_MANAGER__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ESIM_POLICY_MANAGER__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(43378192, 0, &v19);
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
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
    {
LABEL_16:
      v10 = 1;
      goto LABEL_17;
    }
    v9 = 0;
  }
  if ( (v8 & 0x40) != 0 && v9 )
    goto LABEL_16;
  v10 = 0;
LABEL_17:
  v11 = v10 | v8;
  if ( !v4 )
    LODWORD(v19) = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ESIM_POLICY_MANAGER__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ESIM_POLICY_MANAGER__descriptor, 0, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140034280  mov     [rsp+arg_8], rbx
0x140034285  mov     [rsp+arg_10], rbp
0x14003428a  mov     [rsp+arg_0], rcx
0x14003428f  push    rsi
0x140034290  push    rdi
0x140034291  push    r15
0x140034293  sub     rsp, 20h
0x140034297  mov     rsi, cs:Feature_ESIM_POLICY_MANAGER__descriptor
0x14003429e  mov     rdi, rdx
0x1400342a1  mov     qword ptr [rdx], 0
0x1400342a8  mov     eax, [rsi]
0x1400342aa  mov     [rdx], eax
0x1400342ac  and     eax, 6
0x1400342af  cmp     al, 6
0x1400342b1  jz      loc_140034425
0x1400342b7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400342bc  mov     ebp, eax
0x1400342be  mov     dword ptr [rsp+38h+arg_0], 0
0x1400342c6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400342cd  xor     edx, edx
0x1400342cf  test    rax, rax
0x1400342d2  jnz     short loc_1400342E0
0x1400342d4  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400342db  test    rax, rax
0x1400342de  jz      short loc_1400342F1
0x1400342e0  lea     r8, [rsp+38h+arg_0]
0x1400342e5  mov     ecx, 295E610h
0x1400342ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400342ef  mov     edx, eax
0x1400342f1  mov     r8d, edx
0x1400342f4  mov     eax, edx
0x1400342f6  and     r8d, 0FFFFFF3Fh
0x1400342fd  and     edx, 80h
0x140034303  mov     ecx, r8d
0x140034306  mov     r15d, 40h ; '@'
0x14003430c  and     ecx, 3
0x14003430f  and     eax, r15d
0x140034312  shl     ecx, 2
0x140034315  or      ecx, eax
0x140034317  shl     ecx, 2
0x14003431a  or      ecx, edx
0x14003431c  lea     ebx, ds:0[rcx*8]
0x140034323  test    r8d, r8d
0x140034326  jnz     short loc_14003432D
0x140034328  mov     eax, r15d
0x14003432b  jmp     short loc_140034337
0x14003432d  xor     eax, eax
0x14003432f  cmp     r8d, 2
0x140034333  cmovz   eax, r15d
0x140034337  or      ebx, eax
0x140034339  mov     edx, 0C00h
0x14003433e  mov     ecx, ebx
0x140034340  mov     eax, ebx
0x140034342  and     ecx, r15d
0x140034345  and     eax, edx
0x140034347  cmp     eax, edx
0x140034349  jnz     short loc_14003434F
0x14003434b  mov     al, 1
0x14003434d  jmp     short loc_140034355
0x14003434f  test    ecx, ecx
0x140034351  jnz     short loc_140034361
0x140034353  xor     al, al
0x140034355  test    ecx, ecx
0x140034357  jz      short loc_14003435D
0x140034359  test    al, al
0x14003435b  jnz     short loc_140034361
0x14003435d  xor     eax, eax
0x14003435f  jmp     short loc_140034366
0x140034361  mov     eax, 1
0x140034366  or      ebx, eax
0x140034368  test    ebp, ebp
0x14003436a  jnz     short loc_140034370
0x14003436c  mov     dword ptr [rsp+38h+arg_0], ebp
0x140034370  mov     eax, [rdi]
0x140034372  cmp     dword ptr [rsp+38h+arg_0], 0
0x140034377  mov     edx, eax
0x140034379  mov     [rdi], eax
0x14003437b  jz      short loc_1400343B8
0x14003437d  test    dl, 2
0x140034380  jnz     short loc_1400343B8
0x140034382  mov     eax, ebx
0x140034384  xor     eax, edx
0x140034386  and     eax, 180h
0x14003438b  xor     eax, edx
0x14003438d  mov     ecx, eax
0x14003438f  xor     ecx, ebx
0x140034391  and     ecx, r15d
0x140034394  xor     ecx, eax
0x140034396  mov     eax, ecx
0x140034398  xor     eax, ebx
0x14003439a  and     eax, 1
0x14003439d  xor     eax, ecx
0x14003439f  mov     r8d, eax
0x1400343a2  xor     r8d, ebx
0x1400343a5  and     r8d, 800h
0x1400343ac  xor     r8d, eax
0x1400343af  or      r8d, 2
0x1400343b3  mov     [rdi], r8d
0x1400343b6  jmp     short loc_1400343BB
0x1400343b8  mov     r8d, edx
0x1400343bb  mov     r9d, edx
0x1400343be  and     r9d, 4
0x1400343c2  jnz     short loc_1400343D9
0x1400343c4  mov     ecx, ebx
0x1400343c6  xor     ecx, r8d
0x1400343c9  and     ecx, 400h
0x1400343cf  xor     ecx, r8d
0x1400343d2  or      ecx, 4
0x1400343d5  mov     [rdi], ecx
0x1400343d7  jmp     short loc_1400343DC
0x1400343d9  mov     ecx, r8d
0x1400343dc  mov     eax, edx
0x1400343de  lock cmpxchg [rsi], ecx
0x1400343e2  jnz     short loc_140034372
0x1400343e4  test    r9d, r9d
0x1400343e7  jnz     short loc_1400343F6
0x1400343e9  mov     r8d, ebp
0x1400343ec  xor     edx, edx
0x1400343ee  mov     rcx, rsi
0x1400343f1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400343f6  test    byte ptr [rdi], 2
0x1400343f9  jnz     short loc_140034425
0x1400343fb  mov     eax, [rdi]
0x1400343fd  xor     eax, ebx
0x1400343ff  and     eax, 180h
0x140034404  xor     eax, [rdi]
0x140034406  mov     ecx, eax
0x140034408  xor     ecx, ebx
0x14003440a  and     ecx, r15d
0x14003440d  xor     ecx, eax
0x14003440f  mov     edx, ecx
0x140034411  xor     edx, ebx
0x140034413  and     edx, 1
0x140034416  xor     edx, ecx
0x140034418  mov     eax, edx
0x14003441a  xor     eax, ebx
0x14003441c  and     eax, 800h
0x140034421  xor     eax, edx
0x140034423  mov     [rdi], eax
0x140034425  mov     rbx, [rsp+38h+arg_8]
0x14003442a  mov     rax, rdi
0x14003442d  mov     rbp, [rsp+38h+arg_10]
0x140034432  add     rsp, 20h
0x140034436  pop     r15
0x140034438  pop     rdi
0x140034439  pop     rsi
0x14003443a  retn
```
