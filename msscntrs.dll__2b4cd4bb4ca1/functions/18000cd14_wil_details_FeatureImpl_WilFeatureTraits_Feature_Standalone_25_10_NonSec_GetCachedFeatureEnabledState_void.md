# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000cd14`
- end: `0x18000ce81`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013390`

## callees

- `0x180005c18`
- `0x180009714`
- `0x18000cd14`
- `0x180018010`

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
0x18000cd14  mov     [rsp+arg_8], rbx
0x18000cd19  mov     [rsp+arg_10], rbp
0x18000cd1e  mov     [rsp+arg_0], rcx
0x18000cd23  push    rsi
0x18000cd24  push    rdi
0x18000cd25  push    r15
0x18000cd27  sub     rsp, 20h
0x18000cd2b  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000cd32  mov     rbx, rdx
0x18000cd35  mov     qword ptr [rdx], 0
0x18000cd3c  mov     eax, [rsi]
0x18000cd3e  mov     [rdx], eax
0x18000cd40  and     eax, 6
0x18000cd43  cmp     al, 6
0x18000cd45  jz      loc_18000CE6B
0x18000cd4b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000cd50  mov     ebp, eax
0x18000cd52  mov     dword ptr [rsp+38h+arg_0], 0
0x18000cd5a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000cd61  test    rax, rax
0x18000cd64  jz      short loc_18000CD7E
0x18000cd66  lea     r8, [rsp+38h+arg_0]
0x18000cd6b  mov     edx, 3
0x18000cd70  mov     ecx, 2AF34F8h
0x18000cd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd7a  mov     edx, eax
0x18000cd7c  jmp     short loc_18000CD8C
0x18000cd7e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000cd85  test    rax, rax
0x18000cd88  jnz     short loc_18000CD66
0x18000cd8a  xor     edx, edx
0x18000cd8c  mov     r8d, edx
0x18000cd8f  mov     eax, edx
0x18000cd91  and     r8d, 0FFFFFF3Fh
0x18000cd98  and     edx, 80h
0x18000cd9e  mov     ecx, r8d
0x18000cda1  mov     r15d, 40h ; '@'
0x18000cda7  and     ecx, 3
0x18000cdaa  and     eax, r15d
0x18000cdad  shl     ecx, 2
0x18000cdb0  or      ecx, eax
0x18000cdb2  shl     ecx, 2
0x18000cdb5  or      ecx, edx
0x18000cdb7  lea     edi, ds:0[rcx*8]
0x18000cdbe  test    r8d, r8d
0x18000cdc1  jnz     short loc_18000CDC8
0x18000cdc3  mov     eax, r15d
0x18000cdc6  jmp     short loc_18000CDD2
0x18000cdc8  xor     eax, eax
0x18000cdca  cmp     r8d, 2
0x18000cdce  cmovz   eax, r15d
0x18000cdd2  or      edi, eax
0x18000cdd4  mov     eax, [rbx]
0x18000cdd6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000cddb  mov     edx, eax
0x18000cddd  mov     [rbx], eax
0x18000cddf  jz      short loc_18000CE0B
0x18000cde1  test    dl, 2
0x18000cde4  jnz     short loc_18000CE0B
0x18000cde6  xor     eax, edi
0x18000cde8  and     eax, 180h
0x18000cded  xor     eax, edx
0x18000cdef  mov     ecx, eax
0x18000cdf1  xor     ecx, edi
0x18000cdf3  and     ecx, r15d
0x18000cdf6  xor     ecx, eax
0x18000cdf8  or      ecx, 1
0x18000cdfb  mov     eax, ecx
0x18000cdfd  xor     eax, edi
0x18000cdff  and     eax, 800h
0x18000ce04  xor     eax, ecx
0x18000ce06  or      eax, 2
0x18000ce09  mov     [rbx], eax
0x18000ce0b  mov     r8d, edx
0x18000ce0e  mov     ecx, eax
0x18000ce10  and     r8d, 4
0x18000ce14  jnz     short loc_18000CE25
0x18000ce16  xor     ecx, edi
0x18000ce18  and     ecx, 400h
0x18000ce1e  xor     ecx, eax
0x18000ce20  or      ecx, 4
0x18000ce23  mov     [rbx], ecx
0x18000ce25  mov     eax, edx
0x18000ce27  lock cmpxchg [rsi], ecx
0x18000ce2b  jnz     short loc_18000CDD6
0x18000ce2d  test    r8d, r8d
0x18000ce30  jnz     short loc_18000CE42
0x18000ce32  mov     r8d, ebp
0x18000ce35  mov     edx, 3
0x18000ce3a  mov     rcx, rsi
0x18000ce3d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ce42  test    byte ptr [rbx], 2
0x18000ce45  jnz     short loc_18000CE6B
0x18000ce47  mov     eax, [rbx]
0x18000ce49  xor     eax, edi
0x18000ce4b  and     eax, 180h
0x18000ce50  xor     eax, [rbx]
0x18000ce52  mov     ecx, eax
0x18000ce54  xor     ecx, edi
0x18000ce56  and     ecx, r15d
0x18000ce59  xor     ecx, eax
0x18000ce5b  or      ecx, 1
0x18000ce5e  mov     eax, ecx
0x18000ce60  xor     eax, edi
0x18000ce62  and     eax, 800h
0x18000ce67  xor     eax, ecx
0x18000ce69  mov     [rbx], eax
0x18000ce6b  mov     rbp, [rsp+38h+arg_10]
0x18000ce70  mov     rax, rbx
0x18000ce73  mov     rbx, [rsp+38h+arg_8]
0x18000ce78  add     rsp, 20h
0x18000ce7c  pop     r15
0x18000ce7e  pop     rdi
0x18000ce7f  pop     rsi
0x18000ce80  retn
```
