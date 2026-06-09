# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f418`
- end: `0x18000f58f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f9e8`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000f418`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
        3,
        v4);
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
0x18000f418  mov     [rsp+arg_8], rbx
0x18000f41d  mov     [rsp+arg_10], rbp
0x18000f422  mov     [rsp+arg_0], rcx
0x18000f427  push    rsi
0x18000f428  push    rdi
0x18000f429  push    r15
0x18000f42b  sub     rsp, 20h
0x18000f42f  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000f436  mov     rbx, rdx
0x18000f439  mov     qword ptr [rdx], 0
0x18000f440  mov     eax, [rsi]
0x18000f442  mov     [rdx], eax
0x18000f444  and     eax, 6
0x18000f447  cmp     al, 6
0x18000f449  jz      loc_18000F579
0x18000f44f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f454  mov     ebp, eax
0x18000f456  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f45e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f465  test    rax, rax
0x18000f468  jz      short loc_18000F482
0x18000f46a  lea     r8, [rsp+38h+arg_0]
0x18000f46f  mov     edx, 3
0x18000f474  mov     ecx, 3667CA2h
0x18000f479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f47e  mov     edx, eax
0x18000f480  jmp     short loc_18000F490
0x18000f482  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f489  test    rax, rax
0x18000f48c  jnz     short loc_18000F46A
0x18000f48e  xor     edx, edx
0x18000f490  mov     r8d, edx
0x18000f493  mov     eax, edx
0x18000f495  and     r8d, 0FFFFFF3Fh
0x18000f49c  and     edx, 80h
0x18000f4a2  mov     ecx, r8d
0x18000f4a5  mov     r15d, 40h ; '@'
0x18000f4ab  and     ecx, 3
0x18000f4ae  and     eax, r15d
0x18000f4b1  shl     ecx, 2
0x18000f4b4  or      ecx, eax
0x18000f4b6  shl     ecx, 2
0x18000f4b9  or      ecx, edx
0x18000f4bb  lea     edi, ds:0[rcx*8]
0x18000f4c2  test    r8d, r8d
0x18000f4c5  jnz     short loc_18000F4CC
0x18000f4c7  mov     eax, r15d
0x18000f4ca  jmp     short loc_18000F4D6
0x18000f4cc  xor     eax, eax
0x18000f4ce  cmp     r8d, 2
0x18000f4d2  cmovz   eax, r15d
0x18000f4d6  or      edi, eax
0x18000f4d8  mov     eax, [rbx]
0x18000f4da  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f4df  mov     edx, eax
0x18000f4e1  mov     [rbx], eax
0x18000f4e3  jz      short loc_18000F513
0x18000f4e5  test    dl, 2
0x18000f4e8  jnz     short loc_18000F513
0x18000f4ea  mov     eax, edi
0x18000f4ec  xor     eax, edx
0x18000f4ee  and     eax, 180h
0x18000f4f3  xor     eax, edx
0x18000f4f5  mov     ecx, eax
0x18000f4f7  xor     ecx, edi
0x18000f4f9  and     ecx, r15d
0x18000f4fc  xor     ecx, eax
0x18000f4fe  or      ecx, 1
0x18000f501  mov     eax, ecx
0x18000f503  xor     eax, edi
0x18000f505  and     eax, 800h
0x18000f50a  xor     eax, ecx
0x18000f50c  or      eax, 2
0x18000f50f  mov     [rbx], eax
0x18000f511  jmp     short loc_18000F515
0x18000f513  mov     eax, edx
0x18000f515  mov     r8d, edx
0x18000f518  and     r8d, 4
0x18000f51c  jnz     short loc_18000F531
0x18000f51e  mov     ecx, edi
0x18000f520  xor     ecx, eax
0x18000f522  and     ecx, 400h
0x18000f528  xor     ecx, eax
0x18000f52a  or      ecx, 4
0x18000f52d  mov     [rbx], ecx
0x18000f52f  jmp     short loc_18000F533
0x18000f531  mov     ecx, eax
0x18000f533  mov     eax, edx
0x18000f535  lock cmpxchg [rsi], ecx
0x18000f539  jnz     short loc_18000F4DA
0x18000f53b  test    r8d, r8d
0x18000f53e  jnz     short loc_18000F550
0x18000f540  mov     r8d, ebp
0x18000f543  mov     edx, 3
0x18000f548  mov     rcx, rsi
0x18000f54b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f550  test    byte ptr [rbx], 2
0x18000f553  jnz     short loc_18000F579
0x18000f555  mov     eax, [rbx]
0x18000f557  xor     eax, edi
0x18000f559  and     eax, 180h
0x18000f55e  xor     eax, [rbx]
0x18000f560  mov     ecx, eax
0x18000f562  xor     ecx, edi
0x18000f564  and     ecx, r15d
0x18000f567  xor     ecx, eax
0x18000f569  or      ecx, 1
0x18000f56c  mov     eax, ecx
0x18000f56e  xor     eax, edi
0x18000f570  and     eax, 800h
0x18000f575  xor     eax, ecx
0x18000f577  mov     [rbx], eax
0x18000f579  mov     rbp, [rsp+38h+arg_10]
0x18000f57e  mov     rax, rbx
0x18000f581  mov     rbx, [rsp+38h+arg_8]
0x18000f586  add     rsp, 20h
0x18000f58a  pop     r15
0x18000f58c  pop     rdi
0x18000f58d  pop     rsi
0x18000f58e  retn
```
