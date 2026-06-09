# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001256c`
- end: `0x1800126d9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012f48`

## callees

- `0x1800058f8`
- `0x18000b7c8`
- `0x18001256c`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v4);
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
0x18001256c  mov     [rsp+arg_8], rbx
0x180012571  mov     [rsp+arg_10], rbp
0x180012576  mov     [rsp+arg_0], rcx
0x18001257b  push    rsi
0x18001257c  push    rdi
0x18001257d  push    r15
0x18001257f  sub     rsp, 20h
0x180012583  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001258a  mov     rbx, rdx
0x18001258d  mov     qword ptr [rdx], 0
0x180012594  mov     eax, [rsi]
0x180012596  mov     [rdx], eax
0x180012598  and     eax, 6
0x18001259b  cmp     al, 6
0x18001259d  jz      loc_1800126C3
0x1800125a3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800125a8  mov     ebp, eax
0x1800125aa  mov     dword ptr [rsp+38h+arg_0], 0
0x1800125b2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800125b9  test    rax, rax
0x1800125bc  jz      short loc_1800125D6
0x1800125be  lea     r8, [rsp+38h+arg_0]
0x1800125c3  mov     edx, 3
0x1800125c8  mov     ecx, 2AF34F8h
0x1800125cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d2  mov     edx, eax
0x1800125d4  jmp     short loc_1800125E4
0x1800125d6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800125dd  test    rax, rax
0x1800125e0  jnz     short loc_1800125BE
0x1800125e2  xor     edx, edx
0x1800125e4  mov     r8d, edx
0x1800125e7  mov     eax, edx
0x1800125e9  and     r8d, 0FFFFFF3Fh
0x1800125f0  and     edx, 80h
0x1800125f6  mov     ecx, r8d
0x1800125f9  mov     r15d, 40h ; '@'
0x1800125ff  and     ecx, 3
0x180012602  and     eax, r15d
0x180012605  shl     ecx, 2
0x180012608  or      ecx, eax
0x18001260a  shl     ecx, 2
0x18001260d  or      ecx, edx
0x18001260f  lea     edi, ds:0[rcx*8]
0x180012616  test    r8d, r8d
0x180012619  jnz     short loc_180012620
0x18001261b  mov     eax, r15d
0x18001261e  jmp     short loc_18001262A
0x180012620  xor     eax, eax
0x180012622  cmp     r8d, 2
0x180012626  cmovz   eax, r15d
0x18001262a  or      edi, eax
0x18001262c  mov     eax, [rbx]
0x18001262e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012633  mov     edx, eax
0x180012635  mov     [rbx], eax
0x180012637  jz      short loc_180012663
0x180012639  test    dl, 2
0x18001263c  jnz     short loc_180012663
0x18001263e  xor     eax, edi
0x180012640  and     eax, 180h
0x180012645  xor     eax, edx
0x180012647  mov     ecx, eax
0x180012649  xor     ecx, edi
0x18001264b  and     ecx, r15d
0x18001264e  xor     ecx, eax
0x180012650  or      ecx, 1
0x180012653  mov     eax, ecx
0x180012655  xor     eax, edi
0x180012657  and     eax, 800h
0x18001265c  xor     eax, ecx
0x18001265e  or      eax, 2
0x180012661  mov     [rbx], eax
0x180012663  mov     r8d, edx
0x180012666  mov     ecx, eax
0x180012668  and     r8d, 4
0x18001266c  jnz     short loc_18001267D
0x18001266e  xor     ecx, edi
0x180012670  and     ecx, 400h
0x180012676  xor     ecx, eax
0x180012678  or      ecx, 4
0x18001267b  mov     [rbx], ecx
0x18001267d  mov     eax, edx
0x18001267f  lock cmpxchg [rsi], ecx
0x180012683  jnz     short loc_18001262E
0x180012685  test    r8d, r8d
0x180012688  jnz     short loc_18001269A
0x18001268a  mov     r8d, ebp
0x18001268d  mov     edx, 3
0x180012692  mov     rcx, rsi
0x180012695  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001269a  test    byte ptr [rbx], 2
0x18001269d  jnz     short loc_1800126C3
0x18001269f  mov     eax, [rbx]
0x1800126a1  xor     eax, edi
0x1800126a3  and     eax, 180h
0x1800126a8  xor     eax, [rbx]
0x1800126aa  mov     ecx, eax
0x1800126ac  xor     ecx, edi
0x1800126ae  and     ecx, r15d
0x1800126b1  xor     ecx, eax
0x1800126b3  or      ecx, 1
0x1800126b6  mov     eax, ecx
0x1800126b8  xor     eax, edi
0x1800126ba  and     eax, 800h
0x1800126bf  xor     eax, ecx
0x1800126c1  mov     [rbx], eax
0x1800126c3  mov     rbp, [rsp+38h+arg_10]
0x1800126c8  mov     rax, rbx
0x1800126cb  mov     rbx, [rsp+38h+arg_8]
0x1800126d0  add     rsp, 20h
0x1800126d4  pop     r15
0x1800126d6  pop     rdi
0x1800126d7  pop     rsi
0x1800126d8  retn
```
