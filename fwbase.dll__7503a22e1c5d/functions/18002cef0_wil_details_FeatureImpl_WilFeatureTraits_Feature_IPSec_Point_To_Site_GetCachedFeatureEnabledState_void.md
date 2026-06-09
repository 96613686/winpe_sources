# wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetCachedFeatureEnabledState(void)

- ea: `0x18002cef0`
- end: `0x18002d0c7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `471`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dea0`
- `0x18002df50`

## callees

- `0x18001e1d0`
- `0x1800239b0`
- `0x180028210`
- `0x18002cef0`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetCachedFeatureEnabledState(
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
  char v11; // cl
  int v12; // eax
  __int16 v13; // ax
  unsigned __int16 v14; // bx
  signed __int32 v15; // eax
  bool v16; // zf
  signed __int32 v17; // r8d
  int v18; // edx
  int v19; // r9d
  signed __int32 v20; // ecx
  int v21; // ecx
  int v23; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_IPSec_Point_To_Site__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_IPSec_Point_To_Site__descriptor;
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
  v6 = v5(61349125, 3, &v23);
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
    v12 = v10 & 0x40;
  }
  else
  {
    v12 = v10 & 0x40;
    if ( (v10 & 0x40) != 0 )
      goto LABEL_17;
    v11 = 0;
  }
  if ( !v12 || !v11 )
  {
    v13 = 0;
    goto LABEL_18;
  }
LABEL_17:
  v13 = 1;
LABEL_18:
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
    v15 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_IPSec_Point_To_Site__descriptor, v20, v15);
  }
  while ( v17 != v15 );
  if ( !v19 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_IPSec_Point_To_Site__descriptor,
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
0x18002cef0  mov     [rsp+arg_18], rsi
0x18002cef5  push    rdi
0x18002cef6  sub     rsp, 30h
0x18002cefa  mov     rax, cs:__security_cookie
0x18002cf01  xor     rax, rsp
0x18002cf04  mov     [rsp+38h+var_10], rax
0x18002cf09  mov     rsi, cs:Feature_IPSec_Point_To_Site__descriptor
0x18002cf10  mov     rdi, rdx
0x18002cf13  mov     qword ptr [rdx], 0
0x18002cf1a  mov     eax, [rsi]
0x18002cf1c  mov     [rdx], eax
0x18002cf1e  and     eax, 6
0x18002cf21  cmp     al, 6
0x18002cf23  jz      loc_18002D0C2
0x18002cf29  mov     [rsp+38h+arg_0], rbx
0x18002cf2e  mov     [rsp+38h+arg_10], rbp
0x18002cf33  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002cf38  mov     ebp, eax
0x18002cf3a  mov     [rsp+38h+var_18], 0
0x18002cf42  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18002cf49  test    rax, rax
0x18002cf4c  jnz     short loc_18002CF5A
0x18002cf4e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18002cf55  test    rax, rax
0x18002cf58  jz      short loc_18002CFAF
0x18002cf5a  lea     r8, [rsp+38h+var_18]
0x18002cf5f  mov     edx, 3
0x18002cf64  mov     ecx, 3A81D05h
0x18002cf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf6e  mov     r8d, eax
0x18002cf71  mov     edx, eax
0x18002cf73  and     r8d, 0FFFFFF3Fh
0x18002cf7a  and     eax, 40h
0x18002cf7d  and     edx, 80h
0x18002cf83  mov     ecx, r8d
0x18002cf86  and     ecx, 3
0x18002cf89  shl     ecx, 2
0x18002cf8c  or      ecx, eax
0x18002cf8e  shl     ecx, 2
0x18002cf91  or      ecx, edx
0x18002cf93  lea     ebx, ds:0[rcx*8]
0x18002cf9a  test    r8d, r8d
0x18002cf9d  jz      short loc_18002CFB1
0x18002cf9f  xor     eax, eax
0x18002cfa1  mov     ecx, 40h ; '@'
0x18002cfa6  cmp     r8d, 2
0x18002cfaa  cmovz   eax, ecx
0x18002cfad  jmp     short loc_18002CFB3
0x18002cfaf  xor     ebx, ebx
0x18002cfb1  xor     eax, eax
0x18002cfb3  or      ebx, eax
0x18002cfb5  mov     eax, ebx
0x18002cfb7  and     eax, 0C00h
0x18002cfbc  cmp     eax, 0C00h
0x18002cfc1  mov     eax, ebx
0x18002cfc3  jnz     short loc_18002CFCC
0x18002cfc5  mov     cl, 1
0x18002cfc7  and     eax, 40h
0x18002cfca  jmp     short loc_18002CFD3
0x18002cfcc  and     eax, 40h
0x18002cfcf  jnz     short loc_18002CFDF
0x18002cfd1  xor     cl, cl
0x18002cfd3  test    eax, eax
0x18002cfd5  jz      short loc_18002CFDB
0x18002cfd7  test    cl, cl
0x18002cfd9  jnz     short loc_18002CFDF
0x18002cfdb  xor     eax, eax
0x18002cfdd  jmp     short loc_18002CFE4
0x18002cfdf  mov     eax, 1
0x18002cfe4  or      ebx, eax
0x18002cfe6  mov     eax, [rdi]
0x18002cfe8  cmp     [rsp+38h+var_18], 0
0x18002cfed  mov     r8d, eax
0x18002cff0  mov     [rdi], eax
0x18002cff2  jz      short loc_18002D02C
0x18002cff4  test    r8b, 2
0x18002cff8  jnz     short loc_18002D02C
0x18002cffa  mov     eax, ebx
0x18002cffc  xor     eax, r8d
0x18002cfff  and     eax, 180h
0x18002d004  xor     eax, r8d
0x18002d007  mov     ecx, eax
0x18002d009  xor     ecx, ebx
0x18002d00b  and     ecx, 40h
0x18002d00e  xor     ecx, eax
0x18002d010  mov     eax, ecx
0x18002d012  xor     eax, ebx
0x18002d014  and     eax, 1
0x18002d017  xor     eax, ecx
0x18002d019  mov     edx, eax
0x18002d01b  xor     edx, ebx
0x18002d01d  and     edx, 800h
0x18002d023  xor     edx, eax
0x18002d025  or      edx, 2
0x18002d028  mov     [rdi], edx
0x18002d02a  jmp     short loc_18002D02F
0x18002d02c  mov     edx, r8d
0x18002d02f  mov     r9d, r8d
0x18002d032  and     r9d, 4
0x18002d036  jnz     short loc_18002D04B
0x18002d038  mov     ecx, ebx
0x18002d03a  xor     ecx, edx
0x18002d03c  and     ecx, 400h
0x18002d042  xor     ecx, edx
0x18002d044  or      ecx, 4
0x18002d047  mov     [rdi], ecx
0x18002d049  jmp     short loc_18002D04D
0x18002d04b  mov     ecx, edx
0x18002d04d  mov     eax, r8d
0x18002d050  lock cmpxchg [rsi], ecx
0x18002d054  jnz     short loc_18002CFE8
0x18002d056  test    r9d, r9d
0x18002d059  jnz     short loc_18002D06B
0x18002d05b  mov     r8d, ebp
0x18002d05e  mov     edx, 3
0x18002d063  mov     rcx, rsi
0x18002d066  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002d06b  mov     ecx, [rdi]
0x18002d06d  mov     rbp, [rsp+38h+arg_10]
0x18002d072  test    cl, 2
0x18002d075  jnz     short loc_18002D0A2
0x18002d077  mov     eax, ecx
0x18002d079  xor     eax, ebx
0x18002d07b  and     eax, 180h
0x18002d080  xor     eax, ecx
0x18002d082  mov     ecx, eax
0x18002d084  xor     ecx, ebx
0x18002d086  and     ecx, 40h
0x18002d089  xor     ecx, eax
0x18002d08b  mov     edx, ecx
0x18002d08d  xor     edx, ebx
0x18002d08f  and     edx, 1
0x18002d092  xor     edx, ecx
0x18002d094  mov     ecx, edx
0x18002d096  xor     ecx, ebx
0x18002d098  and     ecx, 800h
0x18002d09e  xor     ecx, edx
0x18002d0a0  mov     [rdi], ecx
0x18002d0a2  mov     rbx, [rsp+38h+arg_0]
0x18002d0a7  mov     rax, rdi
0x18002d0aa  mov     rcx, [rsp+38h+var_10]
0x18002d0af  xor     rcx, rsp; StackCookie
0x18002d0b2  call    __security_check_cookie
0x18002d0b7  mov     rsi, [rsp+38h+arg_18]
0x18002d0bc  add     rsp, 30h
0x18002d0c0  pop     rdi
0x18002d0c1  retn
0x18002d0c2  mov     rax, rdi
0x18002d0c5  jmp     short loc_18002D0AA
```
