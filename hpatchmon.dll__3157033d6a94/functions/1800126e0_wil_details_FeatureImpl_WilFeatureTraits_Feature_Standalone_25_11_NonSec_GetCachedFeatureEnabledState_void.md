# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800126e0`
- end: `0x18001284d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c68`

## callees

- `0x1800058f8`
- `0x18000b7c8`
- `0x1800126e0`
- `0x180015010`

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
0x1800126e0  mov     [rsp+arg_8], rbx
0x1800126e5  mov     [rsp+arg_10], rbp
0x1800126ea  mov     [rsp+arg_0], rcx
0x1800126ef  push    rsi
0x1800126f0  push    rdi
0x1800126f1  push    r15
0x1800126f3  sub     rsp, 20h
0x1800126f7  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800126fe  mov     rbx, rdx
0x180012701  mov     qword ptr [rdx], 0
0x180012708  mov     eax, [rsi]
0x18001270a  mov     [rdx], eax
0x18001270c  and     eax, 6
0x18001270f  cmp     al, 6
0x180012711  jz      loc_180012837
0x180012717  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001271c  mov     ebp, eax
0x18001271e  mov     dword ptr [rsp+38h+arg_0], 0
0x180012726  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001272d  test    rax, rax
0x180012730  jz      short loc_18001274A
0x180012732  lea     r8, [rsp+38h+arg_0]
0x180012737  mov     edx, 3
0x18001273c  mov     ecx, 2AF34FDh
0x180012741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012746  mov     edx, eax
0x180012748  jmp     short loc_180012758
0x18001274a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012751  test    rax, rax
0x180012754  jnz     short loc_180012732
0x180012756  xor     edx, edx
0x180012758  mov     r8d, edx
0x18001275b  mov     eax, edx
0x18001275d  and     r8d, 0FFFFFF3Fh
0x180012764  and     edx, 80h
0x18001276a  mov     ecx, r8d
0x18001276d  mov     r15d, 40h ; '@'
0x180012773  and     ecx, 3
0x180012776  and     eax, r15d
0x180012779  shl     ecx, 2
0x18001277c  or      ecx, eax
0x18001277e  shl     ecx, 2
0x180012781  or      ecx, edx
0x180012783  lea     edi, ds:0[rcx*8]
0x18001278a  test    r8d, r8d
0x18001278d  jnz     short loc_180012794
0x18001278f  mov     eax, r15d
0x180012792  jmp     short loc_18001279E
0x180012794  xor     eax, eax
0x180012796  cmp     r8d, 2
0x18001279a  cmovz   eax, r15d
0x18001279e  or      edi, eax
0x1800127a0  mov     eax, [rbx]
0x1800127a2  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800127a7  mov     edx, eax
0x1800127a9  mov     [rbx], eax
0x1800127ab  jz      short loc_1800127D7
0x1800127ad  test    dl, 2
0x1800127b0  jnz     short loc_1800127D7
0x1800127b2  xor     eax, edi
0x1800127b4  and     eax, 180h
0x1800127b9  xor     eax, edx
0x1800127bb  mov     ecx, eax
0x1800127bd  xor     ecx, edi
0x1800127bf  and     ecx, r15d
0x1800127c2  xor     ecx, eax
0x1800127c4  or      ecx, 1
0x1800127c7  mov     eax, ecx
0x1800127c9  xor     eax, edi
0x1800127cb  and     eax, 800h
0x1800127d0  xor     eax, ecx
0x1800127d2  or      eax, 2
0x1800127d5  mov     [rbx], eax
0x1800127d7  mov     r8d, edx
0x1800127da  mov     ecx, eax
0x1800127dc  and     r8d, 4
0x1800127e0  jnz     short loc_1800127F1
0x1800127e2  xor     ecx, edi
0x1800127e4  and     ecx, 400h
0x1800127ea  xor     ecx, eax
0x1800127ec  or      ecx, 4
0x1800127ef  mov     [rbx], ecx
0x1800127f1  mov     eax, edx
0x1800127f3  lock cmpxchg [rsi], ecx
0x1800127f7  jnz     short loc_1800127A2
0x1800127f9  test    r8d, r8d
0x1800127fc  jnz     short loc_18001280E
0x1800127fe  mov     r8d, ebp
0x180012801  mov     edx, 3
0x180012806  mov     rcx, rsi
0x180012809  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001280e  test    byte ptr [rbx], 2
0x180012811  jnz     short loc_180012837
0x180012813  mov     eax, [rbx]
0x180012815  xor     eax, edi
0x180012817  and     eax, 180h
0x18001281c  xor     eax, [rbx]
0x18001281e  mov     ecx, eax
0x180012820  xor     ecx, edi
0x180012822  and     ecx, r15d
0x180012825  xor     ecx, eax
0x180012827  or      ecx, 1
0x18001282a  mov     eax, ecx
0x18001282c  xor     eax, edi
0x18001282e  and     eax, 800h
0x180012833  xor     eax, ecx
0x180012835  mov     [rbx], eax
0x180012837  mov     rbp, [rsp+38h+arg_10]
0x18001283c  mov     rax, rbx
0x18001283f  mov     rbx, [rsp+38h+arg_8]
0x180012844  add     rsp, 20h
0x180012848  pop     r15
0x18001284a  pop     rdi
0x18001284b  pop     rsi
0x18001284c  retn
```
