# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180006184`
- end: `0x1800062fb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006668`
- `0x180012f48`

## callees

- `0x1800058f8`
- `0x180006184`
- `0x18000b7c8`
- `0x180015010`

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
0x180006184  mov     [rsp+arg_8], rbx
0x180006189  mov     [rsp+arg_10], rbp
0x18000618e  mov     [rsp+arg_0], rcx
0x180006193  push    rsi
0x180006194  push    rdi
0x180006195  push    r15
0x180006197  sub     rsp, 20h
0x18000619b  mov     rsi, cs:Feature_ValLabTest__descriptor
0x1800061a2  mov     rbx, rdx
0x1800061a5  mov     qword ptr [rdx], 0
0x1800061ac  mov     eax, [rsi]
0x1800061ae  mov     [rdx], eax
0x1800061b0  and     eax, 6
0x1800061b3  cmp     al, 6
0x1800061b5  jz      loc_1800062E5
0x1800061bb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800061c0  mov     ebp, eax
0x1800061c2  mov     dword ptr [rsp+38h+arg_0], 0
0x1800061ca  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800061d1  test    rax, rax
0x1800061d4  jz      short loc_1800061EE
0x1800061d6  lea     r8, [rsp+38h+arg_0]
0x1800061db  mov     edx, 3
0x1800061e0  mov     ecx, 3667CA2h
0x1800061e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ea  mov     edx, eax
0x1800061ec  jmp     short loc_1800061FC
0x1800061ee  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800061f5  test    rax, rax
0x1800061f8  jnz     short loc_1800061D6
0x1800061fa  xor     edx, edx
0x1800061fc  mov     r8d, edx
0x1800061ff  mov     eax, edx
0x180006201  and     r8d, 0FFFFFF3Fh
0x180006208  and     edx, 80h
0x18000620e  mov     ecx, r8d
0x180006211  mov     r15d, 40h ; '@'
0x180006217  and     ecx, 3
0x18000621a  and     eax, r15d
0x18000621d  shl     ecx, 2
0x180006220  or      ecx, eax
0x180006222  shl     ecx, 2
0x180006225  or      ecx, edx
0x180006227  lea     edi, ds:0[rcx*8]
0x18000622e  test    r8d, r8d
0x180006231  jnz     short loc_180006238
0x180006233  mov     eax, r15d
0x180006236  jmp     short loc_180006242
0x180006238  xor     eax, eax
0x18000623a  cmp     r8d, 2
0x18000623e  cmovz   eax, r15d
0x180006242  or      edi, eax
0x180006244  mov     eax, [rbx]
0x180006246  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000624b  mov     edx, eax
0x18000624d  mov     [rbx], eax
0x18000624f  jz      short loc_18000627F
0x180006251  test    dl, 2
0x180006254  jnz     short loc_18000627F
0x180006256  mov     eax, edi
0x180006258  xor     eax, edx
0x18000625a  and     eax, 180h
0x18000625f  xor     eax, edx
0x180006261  mov     ecx, eax
0x180006263  xor     ecx, edi
0x180006265  and     ecx, r15d
0x180006268  xor     ecx, eax
0x18000626a  or      ecx, 1
0x18000626d  mov     eax, ecx
0x18000626f  xor     eax, edi
0x180006271  and     eax, 800h
0x180006276  xor     eax, ecx
0x180006278  or      eax, 2
0x18000627b  mov     [rbx], eax
0x18000627d  jmp     short loc_180006281
0x18000627f  mov     eax, edx
0x180006281  mov     r8d, edx
0x180006284  and     r8d, 4
0x180006288  jnz     short loc_18000629D
0x18000628a  mov     ecx, edi
0x18000628c  xor     ecx, eax
0x18000628e  and     ecx, 400h
0x180006294  xor     ecx, eax
0x180006296  or      ecx, 4
0x180006299  mov     [rbx], ecx
0x18000629b  jmp     short loc_18000629F
0x18000629d  mov     ecx, eax
0x18000629f  mov     eax, edx
0x1800062a1  lock cmpxchg [rsi], ecx
0x1800062a5  jnz     short loc_180006246
0x1800062a7  test    r8d, r8d
0x1800062aa  jnz     short loc_1800062BC
0x1800062ac  mov     r8d, ebp
0x1800062af  mov     edx, 3
0x1800062b4  mov     rcx, rsi
0x1800062b7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800062bc  test    byte ptr [rbx], 2
0x1800062bf  jnz     short loc_1800062E5
0x1800062c1  mov     eax, [rbx]
0x1800062c3  xor     eax, edi
0x1800062c5  and     eax, 180h
0x1800062ca  xor     eax, [rbx]
0x1800062cc  mov     ecx, eax
0x1800062ce  xor     ecx, edi
0x1800062d0  and     ecx, r15d
0x1800062d3  xor     ecx, eax
0x1800062d5  or      ecx, 1
0x1800062d8  mov     eax, ecx
0x1800062da  xor     eax, edi
0x1800062dc  and     eax, 800h
0x1800062e1  xor     eax, ecx
0x1800062e3  mov     [rbx], eax
0x1800062e5  mov     rbp, [rsp+38h+arg_10]
0x1800062ea  mov     rax, rbx
0x1800062ed  mov     rbx, [rsp+38h+arg_8]
0x1800062f2  add     rsp, 20h
0x1800062f6  pop     r15
0x1800062f8  pop     rdi
0x1800062f9  pop     rsi
0x1800062fa  retn
```
