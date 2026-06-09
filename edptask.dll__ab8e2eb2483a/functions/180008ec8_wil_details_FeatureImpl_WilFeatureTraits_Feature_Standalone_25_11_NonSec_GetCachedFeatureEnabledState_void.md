# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180008ec8`
- end: `0x180009035`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009934`

## callees

- `0x1800084b4`
- `0x180008ec8`
- `0x1800113c4`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036797, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v4);
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
0x180008ec8  mov     [rsp+arg_8], rbx
0x180008ecd  mov     [rsp+arg_10], rbp
0x180008ed2  mov     [rsp+arg_0], rcx
0x180008ed7  push    rsi
0x180008ed8  push    rdi
0x180008ed9  push    r15
0x180008edb  sub     rsp, 20h
0x180008edf  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180008ee6  mov     rbx, rdx
0x180008ee9  mov     qword ptr [rdx], 0
0x180008ef0  mov     eax, [rsi]
0x180008ef2  mov     [rdx], eax
0x180008ef4  and     eax, 6
0x180008ef7  cmp     al, 6
0x180008ef9  jz      loc_18000901F
0x180008eff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008f04  mov     ebp, eax
0x180008f06  mov     dword ptr [rsp+38h+arg_0], 0
0x180008f0e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008f15  test    rax, rax
0x180008f18  jz      short loc_180008F32
0x180008f1a  lea     r8, [rsp+38h+arg_0]
0x180008f1f  mov     edx, 3
0x180008f24  mov     ecx, 2AF34FDh
0x180008f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f2e  mov     edx, eax
0x180008f30  jmp     short loc_180008F40
0x180008f32  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008f39  test    rax, rax
0x180008f3c  jnz     short loc_180008F1A
0x180008f3e  xor     edx, edx
0x180008f40  mov     r8d, edx
0x180008f43  mov     eax, edx
0x180008f45  and     r8d, 0FFFFFF3Fh
0x180008f4c  and     edx, 80h
0x180008f52  mov     ecx, r8d
0x180008f55  mov     r15d, 40h ; '@'
0x180008f5b  and     ecx, 3
0x180008f5e  and     eax, r15d
0x180008f61  shl     ecx, 2
0x180008f64  or      ecx, eax
0x180008f66  shl     ecx, 2
0x180008f69  or      ecx, edx
0x180008f6b  lea     edi, ds:0[rcx*8]
0x180008f72  test    r8d, r8d
0x180008f75  jnz     short loc_180008F7C
0x180008f77  mov     eax, r15d
0x180008f7a  jmp     short loc_180008F86
0x180008f7c  xor     eax, eax
0x180008f7e  cmp     r8d, 2
0x180008f82  cmovz   eax, r15d
0x180008f86  or      edi, eax
0x180008f88  mov     eax, [rbx]
0x180008f8a  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008f8f  mov     edx, eax
0x180008f91  mov     [rbx], eax
0x180008f93  jz      short loc_180008FBF
0x180008f95  test    dl, 2
0x180008f98  jnz     short loc_180008FBF
0x180008f9a  xor     eax, edi
0x180008f9c  and     eax, 180h
0x180008fa1  xor     eax, edx
0x180008fa3  mov     ecx, eax
0x180008fa5  xor     ecx, edi
0x180008fa7  and     ecx, r15d
0x180008faa  xor     ecx, eax
0x180008fac  or      ecx, 1
0x180008faf  mov     eax, ecx
0x180008fb1  xor     eax, edi
0x180008fb3  and     eax, 800h
0x180008fb8  xor     eax, ecx
0x180008fba  or      eax, 2
0x180008fbd  mov     [rbx], eax
0x180008fbf  mov     r8d, edx
0x180008fc2  mov     ecx, eax
0x180008fc4  and     r8d, 4
0x180008fc8  jnz     short loc_180008FD9
0x180008fca  xor     ecx, edi
0x180008fcc  and     ecx, 400h
0x180008fd2  xor     ecx, eax
0x180008fd4  or      ecx, 4
0x180008fd7  mov     [rbx], ecx
0x180008fd9  mov     eax, edx
0x180008fdb  lock cmpxchg [rsi], ecx
0x180008fdf  jnz     short loc_180008F8A
0x180008fe1  test    r8d, r8d
0x180008fe4  jnz     short loc_180008FF6
0x180008fe6  mov     r8d, ebp
0x180008fe9  mov     edx, 3
0x180008fee  mov     rcx, rsi
0x180008ff1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008ff6  test    byte ptr [rbx], 2
0x180008ff9  jnz     short loc_18000901F
0x180008ffb  mov     eax, [rbx]
0x180008ffd  xor     eax, edi
0x180008fff  and     eax, 180h
0x180009004  xor     eax, [rbx]
0x180009006  mov     ecx, eax
0x180009008  xor     ecx, edi
0x18000900a  and     ecx, r15d
0x18000900d  xor     ecx, eax
0x18000900f  or      ecx, 1
0x180009012  mov     eax, ecx
0x180009014  xor     eax, edi
0x180009016  and     eax, 800h
0x18000901b  xor     eax, ecx
0x18000901d  mov     [rbx], eax
0x18000901f  mov     rbp, [rsp+38h+arg_10]
0x180009024  mov     rax, rbx
0x180009027  mov     rbx, [rsp+38h+arg_8]
0x18000902c  add     rsp, 20h
0x180009030  pop     r15
0x180009032  pop     rdi
0x180009033  pop     rsi
0x180009034  retn
```
