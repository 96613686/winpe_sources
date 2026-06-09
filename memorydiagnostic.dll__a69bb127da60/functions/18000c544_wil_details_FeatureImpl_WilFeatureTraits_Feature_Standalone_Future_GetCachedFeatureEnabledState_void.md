# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c544`
- end: `0x18000c6bb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cbbc`

## callees

- `0x18000ad30`
- `0x18000c544`
- `0x1800135a0`
- `0x180023010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v4);
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
0x18000c544  mov     [rsp+arg_8], rbx
0x18000c549  mov     [rsp+arg_10], rbp
0x18000c54e  mov     [rsp+arg_0], rcx
0x18000c553  push    rsi
0x18000c554  push    rdi
0x18000c555  push    r15
0x18000c557  sub     rsp, 20h
0x18000c55b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18000c562  mov     rbx, rdx
0x18000c565  mov     qword ptr [rdx], 0
0x18000c56c  mov     eax, [rsi]
0x18000c56e  mov     [rdx], eax
0x18000c570  and     eax, 6
0x18000c573  cmp     al, 6
0x18000c575  jz      loc_18000C6A5
0x18000c57b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c580  mov     ebp, eax
0x18000c582  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c58a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000c591  test    rax, rax
0x18000c594  jz      short loc_18000C5AE
0x18000c596  lea     r8, [rsp+38h+arg_0]
0x18000c59b  mov     edx, 3
0x18000c5a0  mov     ecx, 2F29A04h
0x18000c5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5aa  mov     edx, eax
0x18000c5ac  jmp     short loc_18000C5BC
0x18000c5ae  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000c5b5  test    rax, rax
0x18000c5b8  jnz     short loc_18000C596
0x18000c5ba  xor     edx, edx
0x18000c5bc  mov     r8d, edx
0x18000c5bf  mov     eax, edx
0x18000c5c1  and     r8d, 0FFFFFF3Fh
0x18000c5c8  and     edx, 80h
0x18000c5ce  mov     ecx, r8d
0x18000c5d1  mov     r15d, 40h ; '@'
0x18000c5d7  and     ecx, 3
0x18000c5da  and     eax, r15d
0x18000c5dd  shl     ecx, 2
0x18000c5e0  or      ecx, eax
0x18000c5e2  shl     ecx, 2
0x18000c5e5  or      ecx, edx
0x18000c5e7  lea     edi, ds:0[rcx*8]
0x18000c5ee  test    r8d, r8d
0x18000c5f1  jnz     short loc_18000C5F8
0x18000c5f3  mov     eax, r15d
0x18000c5f6  jmp     short loc_18000C602
0x18000c5f8  xor     eax, eax
0x18000c5fa  cmp     r8d, 2
0x18000c5fe  cmovz   eax, r15d
0x18000c602  or      edi, eax
0x18000c604  mov     eax, [rbx]
0x18000c606  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c60b  mov     edx, eax
0x18000c60d  mov     [rbx], eax
0x18000c60f  jz      short loc_18000C63F
0x18000c611  test    dl, 2
0x18000c614  jnz     short loc_18000C63F
0x18000c616  mov     eax, edi
0x18000c618  xor     eax, edx
0x18000c61a  and     eax, 180h
0x18000c61f  xor     eax, edx
0x18000c621  mov     ecx, eax
0x18000c623  xor     ecx, edi
0x18000c625  and     ecx, r15d
0x18000c628  xor     ecx, eax
0x18000c62a  or      ecx, 1
0x18000c62d  mov     eax, ecx
0x18000c62f  xor     eax, edi
0x18000c631  and     eax, 800h
0x18000c636  xor     eax, ecx
0x18000c638  or      eax, 2
0x18000c63b  mov     [rbx], eax
0x18000c63d  jmp     short loc_18000C641
0x18000c63f  mov     eax, edx
0x18000c641  mov     r8d, edx
0x18000c644  and     r8d, 4
0x18000c648  jnz     short loc_18000C65D
0x18000c64a  mov     ecx, edi
0x18000c64c  xor     ecx, eax
0x18000c64e  and     ecx, 400h
0x18000c654  xor     ecx, eax
0x18000c656  or      ecx, 4
0x18000c659  mov     [rbx], ecx
0x18000c65b  jmp     short loc_18000C65F
0x18000c65d  mov     ecx, eax
0x18000c65f  mov     eax, edx
0x18000c661  lock cmpxchg [rsi], ecx
0x18000c665  jnz     short loc_18000C606
0x18000c667  test    r8d, r8d
0x18000c66a  jnz     short loc_18000C67C
0x18000c66c  mov     r8d, ebp
0x18000c66f  mov     edx, 3
0x18000c674  mov     rcx, rsi
0x18000c677  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c67c  test    byte ptr [rbx], 2
0x18000c67f  jnz     short loc_18000C6A5
0x18000c681  mov     eax, [rbx]
0x18000c683  xor     eax, edi
0x18000c685  and     eax, 180h
0x18000c68a  xor     eax, [rbx]
0x18000c68c  mov     ecx, eax
0x18000c68e  xor     ecx, edi
0x18000c690  and     ecx, r15d
0x18000c693  xor     ecx, eax
0x18000c695  or      ecx, 1
0x18000c698  mov     eax, ecx
0x18000c69a  xor     eax, edi
0x18000c69c  and     eax, 800h
0x18000c6a1  xor     eax, ecx
0x18000c6a3  mov     [rbx], eax
0x18000c6a5  mov     rbp, [rsp+38h+arg_10]
0x18000c6aa  mov     rax, rbx
0x18000c6ad  mov     rbx, [rsp+38h+arg_8]
0x18000c6b2  add     rsp, 20h
0x18000c6b6  pop     r15
0x18000c6b8  pop     rdi
0x18000c6b9  pop     rsi
0x18000c6ba  retn
```
