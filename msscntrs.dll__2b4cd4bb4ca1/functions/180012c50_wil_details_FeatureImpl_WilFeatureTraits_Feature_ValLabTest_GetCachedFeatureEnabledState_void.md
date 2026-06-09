# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180012c50`
- end: `0x180012dc7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013390`

## callees

- `0x180005c18`
- `0x180009714`
- `0x180012c50`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
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
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180012c50  mov     [rsp+arg_8], rbx
0x180012c55  mov     [rsp+arg_10], rbp
0x180012c5a  mov     [rsp+arg_0], rcx
0x180012c5f  push    rsi
0x180012c60  push    rdi
0x180012c61  push    r15
0x180012c63  sub     rsp, 20h
0x180012c67  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180012c6e  mov     rbx, rdx
0x180012c71  mov     qword ptr [rdx], 0
0x180012c78  mov     eax, [rsi]
0x180012c7a  mov     [rdx], eax
0x180012c7c  and     eax, 6
0x180012c7f  cmp     al, 6
0x180012c81  jz      loc_180012DB1
0x180012c87  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012c8c  mov     ebp, eax
0x180012c8e  mov     dword ptr [rsp+38h+arg_0], 0
0x180012c96  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012c9d  test    rax, rax
0x180012ca0  jz      short loc_180012CBA
0x180012ca2  lea     r8, [rsp+38h+arg_0]
0x180012ca7  mov     edx, 3
0x180012cac  mov     ecx, 3667CA2h
0x180012cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb6  mov     edx, eax
0x180012cb8  jmp     short loc_180012CC8
0x180012cba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012cc1  test    rax, rax
0x180012cc4  jnz     short loc_180012CA2
0x180012cc6  xor     edx, edx
0x180012cc8  mov     r8d, edx
0x180012ccb  mov     eax, edx
0x180012ccd  and     r8d, 0FFFFFF3Fh
0x180012cd4  and     edx, 80h
0x180012cda  mov     ecx, r8d
0x180012cdd  mov     r15d, 40h ; '@'
0x180012ce3  and     ecx, 3
0x180012ce6  and     eax, r15d
0x180012ce9  shl     ecx, 2
0x180012cec  or      ecx, eax
0x180012cee  shl     ecx, 2
0x180012cf1  or      ecx, edx
0x180012cf3  lea     edi, ds:0[rcx*8]
0x180012cfa  test    r8d, r8d
0x180012cfd  jnz     short loc_180012D04
0x180012cff  mov     eax, r15d
0x180012d02  jmp     short loc_180012D0E
0x180012d04  xor     eax, eax
0x180012d06  cmp     r8d, 2
0x180012d0a  cmovz   eax, r15d
0x180012d0e  or      edi, eax
0x180012d10  mov     eax, [rbx]
0x180012d12  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012d17  mov     edx, eax
0x180012d19  mov     [rbx], eax
0x180012d1b  jz      short loc_180012D4B
0x180012d1d  test    dl, 2
0x180012d20  jnz     short loc_180012D4B
0x180012d22  mov     eax, edi
0x180012d24  xor     eax, edx
0x180012d26  and     eax, 180h
0x180012d2b  xor     eax, edx
0x180012d2d  mov     ecx, eax
0x180012d2f  xor     ecx, edi
0x180012d31  and     ecx, r15d
0x180012d34  xor     ecx, eax
0x180012d36  or      ecx, 1
0x180012d39  mov     eax, ecx
0x180012d3b  xor     eax, edi
0x180012d3d  and     eax, 800h
0x180012d42  xor     eax, ecx
0x180012d44  or      eax, 2
0x180012d47  mov     [rbx], eax
0x180012d49  jmp     short loc_180012D4D
0x180012d4b  mov     eax, edx
0x180012d4d  mov     r8d, edx
0x180012d50  and     r8d, 4
0x180012d54  jnz     short loc_180012D69
0x180012d56  mov     ecx, edi
0x180012d58  xor     ecx, eax
0x180012d5a  and     ecx, 400h
0x180012d60  xor     ecx, eax
0x180012d62  or      ecx, 4
0x180012d65  mov     [rbx], ecx
0x180012d67  jmp     short loc_180012D6B
0x180012d69  mov     ecx, eax
0x180012d6b  mov     eax, edx
0x180012d6d  lock cmpxchg [rsi], ecx
0x180012d71  jnz     short loc_180012D12
0x180012d73  test    r8d, r8d
0x180012d76  jnz     short loc_180012D88
0x180012d78  mov     r8d, ebp
0x180012d7b  mov     edx, 3
0x180012d80  mov     rcx, rsi
0x180012d83  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012d88  test    byte ptr [rbx], 2
0x180012d8b  jnz     short loc_180012DB1
0x180012d8d  mov     eax, [rbx]
0x180012d8f  xor     eax, edi
0x180012d91  and     eax, 180h
0x180012d96  xor     eax, [rbx]
0x180012d98  mov     ecx, eax
0x180012d9a  xor     ecx, edi
0x180012d9c  and     ecx, r15d
0x180012d9f  xor     ecx, eax
0x180012da1  or      ecx, 1
0x180012da4  mov     eax, ecx
0x180012da6  xor     eax, edi
0x180012da8  and     eax, 800h
0x180012dad  xor     eax, ecx
0x180012daf  mov     [rbx], eax
0x180012db1  mov     rbp, [rsp+38h+arg_10]
0x180012db6  mov     rax, rbx
0x180012db9  mov     rbx, [rsp+38h+arg_8]
0x180012dbe  add     rsp, 20h
0x180012dc2  pop     r15
0x180012dc4  pop     rdi
0x180012dc5  pop     rsi
0x180012dc6  retn
```
