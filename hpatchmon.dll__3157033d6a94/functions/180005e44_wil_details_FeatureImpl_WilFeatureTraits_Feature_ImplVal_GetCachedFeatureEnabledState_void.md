# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)

- ea: `0x180005e44`
- end: `0x180005fbb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006520`

## callees

- `0x1800058f8`
- `0x180005e44`
- `0x18000b7c8`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ImplVal__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ImplVal__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(54237993, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ImplVal__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ImplVal__descriptor, 3, v4);
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
0x180005e44  mov     [rsp+arg_8], rbx
0x180005e49  mov     [rsp+arg_10], rbp
0x180005e4e  mov     [rsp+arg_0], rcx
0x180005e53  push    rsi
0x180005e54  push    rdi
0x180005e55  push    r15
0x180005e57  sub     rsp, 20h
0x180005e5b  mov     rsi, cs:Feature_ImplVal__descriptor
0x180005e62  mov     rbx, rdx
0x180005e65  mov     qword ptr [rdx], 0
0x180005e6c  mov     eax, [rsi]
0x180005e6e  mov     [rdx], eax
0x180005e70  and     eax, 6
0x180005e73  cmp     al, 6
0x180005e75  jz      loc_180005FA5
0x180005e7b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005e80  mov     ebp, eax
0x180005e82  mov     dword ptr [rsp+38h+arg_0], 0
0x180005e8a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180005e91  test    rax, rax
0x180005e94  jz      short loc_180005EAE
0x180005e96  lea     r8, [rsp+38h+arg_0]
0x180005e9b  mov     edx, 3
0x180005ea0  mov     ecx, 33B9B29h
0x180005ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eaa  mov     edx, eax
0x180005eac  jmp     short loc_180005EBC
0x180005eae  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180005eb5  test    rax, rax
0x180005eb8  jnz     short loc_180005E96
0x180005eba  xor     edx, edx
0x180005ebc  mov     r8d, edx
0x180005ebf  mov     eax, edx
0x180005ec1  and     r8d, 0FFFFFF3Fh
0x180005ec8  and     edx, 80h
0x180005ece  mov     ecx, r8d
0x180005ed1  mov     r15d, 40h ; '@'
0x180005ed7  and     ecx, 3
0x180005eda  and     eax, r15d
0x180005edd  shl     ecx, 2
0x180005ee0  or      ecx, eax
0x180005ee2  shl     ecx, 2
0x180005ee5  or      ecx, edx
0x180005ee7  lea     edi, ds:0[rcx*8]
0x180005eee  test    r8d, r8d
0x180005ef1  jnz     short loc_180005EF8
0x180005ef3  mov     eax, r15d
0x180005ef6  jmp     short loc_180005F02
0x180005ef8  xor     eax, eax
0x180005efa  cmp     r8d, 2
0x180005efe  cmovz   eax, r15d
0x180005f02  or      edi, eax
0x180005f04  mov     eax, [rbx]
0x180005f06  cmp     dword ptr [rsp+38h+arg_0], 0
0x180005f0b  mov     edx, eax
0x180005f0d  mov     [rbx], eax
0x180005f0f  jz      short loc_180005F3F
0x180005f11  test    dl, 2
0x180005f14  jnz     short loc_180005F3F
0x180005f16  mov     eax, edi
0x180005f18  xor     eax, edx
0x180005f1a  and     eax, 180h
0x180005f1f  xor     eax, edx
0x180005f21  mov     ecx, eax
0x180005f23  xor     ecx, edi
0x180005f25  and     ecx, r15d
0x180005f28  xor     ecx, eax
0x180005f2a  or      ecx, 1
0x180005f2d  mov     eax, ecx
0x180005f2f  xor     eax, edi
0x180005f31  and     eax, 800h
0x180005f36  xor     eax, ecx
0x180005f38  or      eax, 2
0x180005f3b  mov     [rbx], eax
0x180005f3d  jmp     short loc_180005F41
0x180005f3f  mov     eax, edx
0x180005f41  mov     r8d, edx
0x180005f44  and     r8d, 4
0x180005f48  jnz     short loc_180005F5D
0x180005f4a  mov     ecx, edi
0x180005f4c  xor     ecx, eax
0x180005f4e  and     ecx, 400h
0x180005f54  xor     ecx, eax
0x180005f56  or      ecx, 4
0x180005f59  mov     [rbx], ecx
0x180005f5b  jmp     short loc_180005F5F
0x180005f5d  mov     ecx, eax
0x180005f5f  mov     eax, edx
0x180005f61  lock cmpxchg [rsi], ecx
0x180005f65  jnz     short loc_180005F06
0x180005f67  test    r8d, r8d
0x180005f6a  jnz     short loc_180005F7C
0x180005f6c  mov     r8d, ebp
0x180005f6f  mov     edx, 3
0x180005f74  mov     rcx, rsi
0x180005f77  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005f7c  test    byte ptr [rbx], 2
0x180005f7f  jnz     short loc_180005FA5
0x180005f81  mov     eax, [rbx]
0x180005f83  xor     eax, edi
0x180005f85  and     eax, 180h
0x180005f8a  xor     eax, [rbx]
0x180005f8c  mov     ecx, eax
0x180005f8e  xor     ecx, edi
0x180005f90  and     ecx, r15d
0x180005f93  xor     ecx, eax
0x180005f95  or      ecx, 1
0x180005f98  mov     eax, ecx
0x180005f9a  xor     eax, edi
0x180005f9c  and     eax, 800h
0x180005fa1  xor     eax, ecx
0x180005fa3  mov     [rbx], eax
0x180005fa5  mov     rbp, [rsp+38h+arg_10]
0x180005faa  mov     rax, rbx
0x180005fad  mov     rbx, [rsp+38h+arg_8]
0x180005fb2  add     rsp, 20h
0x180005fb6  pop     r15
0x180005fb8  pop     rdi
0x180005fb9  pop     rsi
0x180005fba  retn
```
