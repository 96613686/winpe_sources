# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012854`
- end: `0x1800129c1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012dd8`

## callees

- `0x1800058f8`
- `0x18000b7c8`
- `0x180012854`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599532, 3, &v14);
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
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v4);
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
0x180012854  mov     [rsp+arg_8], rbx
0x180012859  mov     [rsp+arg_10], rbp
0x18001285e  mov     [rsp+arg_0], rcx
0x180012863  push    rsi
0x180012864  push    rdi
0x180012865  push    r15
0x180012867  sub     rsp, 20h
0x18001286b  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180012872  mov     rbx, rdx
0x180012875  mov     qword ptr [rdx], 0
0x18001287c  mov     eax, [rsi]
0x18001287e  mov     [rdx], eax
0x180012880  and     eax, 6
0x180012883  cmp     al, 6
0x180012885  jz      loc_1800129AB
0x18001288b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012890  mov     ebp, eax
0x180012892  mov     dword ptr [rsp+38h+arg_0], 0
0x18001289a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800128a1  test    rax, rax
0x1800128a4  jz      short loc_1800128BE
0x1800128a6  lea     r8, [rsp+38h+arg_0]
0x1800128ab  mov     edx, 3
0x1800128b0  mov     ecx, 37E286Ch
0x1800128b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128ba  mov     edx, eax
0x1800128bc  jmp     short loc_1800128CC
0x1800128be  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800128c5  test    rax, rax
0x1800128c8  jnz     short loc_1800128A6
0x1800128ca  xor     edx, edx
0x1800128cc  mov     r8d, edx
0x1800128cf  mov     eax, edx
0x1800128d1  and     r8d, 0FFFFFF3Fh
0x1800128d8  and     edx, 80h
0x1800128de  mov     ecx, r8d
0x1800128e1  mov     r15d, 40h ; '@'
0x1800128e7  and     ecx, 3
0x1800128ea  and     eax, r15d
0x1800128ed  shl     ecx, 2
0x1800128f0  or      ecx, eax
0x1800128f2  shl     ecx, 2
0x1800128f5  or      ecx, edx
0x1800128f7  lea     edi, ds:0[rcx*8]
0x1800128fe  test    r8d, r8d
0x180012901  jnz     short loc_180012908
0x180012903  mov     eax, r15d
0x180012906  jmp     short loc_180012912
0x180012908  xor     eax, eax
0x18001290a  cmp     r8d, 2
0x18001290e  cmovz   eax, r15d
0x180012912  or      edi, eax
0x180012914  mov     eax, [rbx]
0x180012916  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001291b  mov     edx, eax
0x18001291d  mov     [rbx], eax
0x18001291f  jz      short loc_18001294B
0x180012921  test    dl, 2
0x180012924  jnz     short loc_18001294B
0x180012926  xor     eax, edi
0x180012928  and     eax, 180h
0x18001292d  xor     eax, edx
0x18001292f  mov     ecx, eax
0x180012931  xor     ecx, edi
0x180012933  and     ecx, r15d
0x180012936  xor     ecx, eax
0x180012938  or      ecx, 1
0x18001293b  mov     eax, ecx
0x18001293d  xor     eax, edi
0x18001293f  and     eax, 800h
0x180012944  xor     eax, ecx
0x180012946  or      eax, 2
0x180012949  mov     [rbx], eax
0x18001294b  mov     r8d, edx
0x18001294e  mov     ecx, eax
0x180012950  and     r8d, 4
0x180012954  jnz     short loc_180012965
0x180012956  xor     ecx, edi
0x180012958  and     ecx, 400h
0x18001295e  xor     ecx, eax
0x180012960  or      ecx, 4
0x180012963  mov     [rbx], ecx
0x180012965  mov     eax, edx
0x180012967  lock cmpxchg [rsi], ecx
0x18001296b  jnz     short loc_180012916
0x18001296d  test    r8d, r8d
0x180012970  jnz     short loc_180012982
0x180012972  mov     r8d, ebp
0x180012975  mov     edx, 3
0x18001297a  mov     rcx, rsi
0x18001297d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012982  test    byte ptr [rbx], 2
0x180012985  jnz     short loc_1800129AB
0x180012987  mov     eax, [rbx]
0x180012989  xor     eax, edi
0x18001298b  and     eax, 180h
0x180012990  xor     eax, [rbx]
0x180012992  mov     ecx, eax
0x180012994  xor     ecx, edi
0x180012996  and     ecx, r15d
0x180012999  xor     ecx, eax
0x18001299b  or      ecx, 1
0x18001299e  mov     eax, ecx
0x1800129a0  xor     eax, edi
0x1800129a2  and     eax, 800h
0x1800129a7  xor     eax, ecx
0x1800129a9  mov     [rbx], eax
0x1800129ab  mov     rbp, [rsp+38h+arg_10]
0x1800129b0  mov     rax, rbx
0x1800129b3  mov     rbx, [rsp+38h+arg_8]
0x1800129b8  add     rsp, 20h
0x1800129bc  pop     r15
0x1800129be  pop     rdi
0x1800129bf  pop     rsi
0x1800129c0  retn
```
