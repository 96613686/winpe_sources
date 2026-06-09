# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b950`
- end: `0x18001bb06`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Tls13InTeap@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `438`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023b94`

## callees

- `0x180009e0c`
- `0x18000bbb0`
- `0x18001b950`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Tls13InTeap>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Tls13InTeap__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Tls13InTeap__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(31308506, 0, &v19);
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
    {
LABEL_14:
      v10 = 1;
      goto LABEL_15;
    }
    v9 = 0;
  }
  if ( (v8 & 0x40) != 0 && v9 )
    goto LABEL_14;
  v10 = 0;
LABEL_15:
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Tls13InTeap__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Tls13InTeap__descriptor, 0, v4);
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
0x18001b950  mov     [rsp+arg_8], rbx
0x18001b955  mov     [rsp+arg_10], rbp
0x18001b95a  mov     [rsp+arg_0], rcx
0x18001b95f  push    rsi
0x18001b960  push    rdi
0x18001b961  push    r15
0x18001b963  sub     rsp, 20h
0x18001b967  mov     rsi, cs:Feature_Tls13InTeap__descriptor
0x18001b96e  mov     rdi, rdx
0x18001b971  mov     qword ptr [rdx], 0
0x18001b978  mov     eax, [rsi]
0x18001b97a  mov     [rdx], eax
0x18001b97c  and     eax, 6
0x18001b97f  cmp     al, 6
0x18001b981  jz      loc_18001BAF0
0x18001b987  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b98c  mov     ebp, eax
0x18001b98e  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b996  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001b99d  xor     edx, edx
0x18001b99f  test    rax, rax
0x18001b9a2  jnz     short loc_18001B9B0
0x18001b9a4  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001b9ab  test    rax, rax
0x18001b9ae  jz      short loc_18001B9C1
0x18001b9b0  lea     r8, [rsp+38h+arg_0]
0x18001b9b5  mov     ecx, 1DDBADAh
0x18001b9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9bf  mov     edx, eax
0x18001b9c1  mov     r8d, edx
0x18001b9c4  mov     eax, edx
0x18001b9c6  and     r8d, 0FFFFFF3Fh
0x18001b9cd  and     edx, 80h
0x18001b9d3  mov     ecx, r8d
0x18001b9d6  mov     r15d, 40h ; '@'
0x18001b9dc  and     ecx, 3
0x18001b9df  and     eax, r15d
0x18001b9e2  shl     ecx, 2
0x18001b9e5  or      ecx, eax
0x18001b9e7  xor     eax, eax
0x18001b9e9  shl     ecx, 2
0x18001b9ec  or      ecx, edx
0x18001b9ee  lea     ebx, ds:0[rcx*8]
0x18001b9f5  test    r8d, r8d
0x18001b9f8  jz      short loc_18001BA02
0x18001b9fa  cmp     r8d, 2
0x18001b9fe  cmovz   eax, r15d
0x18001ba02  or      ebx, eax
0x18001ba04  mov     edx, 0C00h
0x18001ba09  mov     ecx, ebx
0x18001ba0b  mov     eax, ebx
0x18001ba0d  and     ecx, r15d
0x18001ba10  and     eax, edx
0x18001ba12  cmp     eax, edx
0x18001ba14  jnz     short loc_18001BA1A
0x18001ba16  mov     al, 1
0x18001ba18  jmp     short loc_18001BA20
0x18001ba1a  test    ecx, ecx
0x18001ba1c  jnz     short loc_18001BA2C
0x18001ba1e  xor     al, al
0x18001ba20  test    ecx, ecx
0x18001ba22  jz      short loc_18001BA28
0x18001ba24  test    al, al
0x18001ba26  jnz     short loc_18001BA2C
0x18001ba28  xor     eax, eax
0x18001ba2a  jmp     short loc_18001BA31
0x18001ba2c  mov     eax, 1
0x18001ba31  or      ebx, eax
0x18001ba33  test    ebp, ebp
0x18001ba35  jnz     short loc_18001BA3B
0x18001ba37  mov     dword ptr [rsp+38h+arg_0], ebp
0x18001ba3b  mov     eax, [rdi]
0x18001ba3d  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001ba42  mov     edx, eax
0x18001ba44  mov     [rdi], eax
0x18001ba46  jz      short loc_18001BA83
0x18001ba48  test    dl, 2
0x18001ba4b  jnz     short loc_18001BA83
0x18001ba4d  mov     eax, ebx
0x18001ba4f  xor     eax, edx
0x18001ba51  and     eax, 180h
0x18001ba56  xor     eax, edx
0x18001ba58  mov     ecx, eax
0x18001ba5a  xor     ecx, ebx
0x18001ba5c  and     ecx, r15d
0x18001ba5f  xor     ecx, eax
0x18001ba61  mov     eax, ecx
0x18001ba63  xor     eax, ebx
0x18001ba65  and     eax, 1
0x18001ba68  xor     eax, ecx
0x18001ba6a  mov     r8d, eax
0x18001ba6d  xor     r8d, ebx
0x18001ba70  and     r8d, 800h
0x18001ba77  xor     r8d, eax
0x18001ba7a  or      r8d, 2
0x18001ba7e  mov     [rdi], r8d
0x18001ba81  jmp     short loc_18001BA86
0x18001ba83  mov     r8d, edx
0x18001ba86  mov     r9d, edx
0x18001ba89  and     r9d, 4
0x18001ba8d  jnz     short loc_18001BAA4
0x18001ba8f  mov     ecx, ebx
0x18001ba91  xor     ecx, r8d
0x18001ba94  and     ecx, 400h
0x18001ba9a  xor     ecx, r8d
0x18001ba9d  or      ecx, 4
0x18001baa0  mov     [rdi], ecx
0x18001baa2  jmp     short loc_18001BAA7
0x18001baa4  mov     ecx, r8d
0x18001baa7  mov     eax, edx
0x18001baa9  lock cmpxchg [rsi], ecx
0x18001baad  jnz     short loc_18001BA3D
0x18001baaf  test    r9d, r9d
0x18001bab2  jnz     short loc_18001BAC1
0x18001bab4  mov     r8d, ebp
0x18001bab7  xor     edx, edx
0x18001bab9  mov     rcx, rsi
0x18001babc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001bac1  test    byte ptr [rdi], 2
0x18001bac4  jnz     short loc_18001BAF0
0x18001bac6  mov     eax, [rdi]
0x18001bac8  xor     eax, ebx
0x18001baca  and     eax, 180h
0x18001bacf  xor     eax, [rdi]
0x18001bad1  mov     ecx, eax
0x18001bad3  xor     ecx, ebx
0x18001bad5  and     ecx, r15d
0x18001bad8  xor     ecx, eax
0x18001bada  mov     edx, ecx
0x18001badc  xor     edx, ebx
0x18001bade  and     edx, 1
0x18001bae1  xor     edx, ecx
0x18001bae3  mov     eax, edx
0x18001bae5  xor     eax, ebx
0x18001bae7  and     eax, 800h
0x18001baec  xor     eax, edx
0x18001baee  mov     [rdi], eax
0x18001baf0  mov     rbx, [rsp+38h+arg_8]
0x18001baf5  mov     rax, rdi
0x18001baf8  mov     rbp, [rsp+38h+arg_10]
0x18001bafd  add     rsp, 20h
0x18001bb01  pop     r15
0x18001bb03  pop     rdi
0x18001bb04  pop     rsi
0x18001bb05  retn
```
