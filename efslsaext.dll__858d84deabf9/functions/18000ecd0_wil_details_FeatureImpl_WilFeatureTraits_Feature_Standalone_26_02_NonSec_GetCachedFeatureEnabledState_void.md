# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ecd0`
- end: `0x18000ee3d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f598`

## callees

- `0x18000426c`
- `0x180005e58`
- `0x18000ecd0`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599550, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
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
0x18000ecd0  mov     [rsp+arg_8], rbx
0x18000ecd5  mov     [rsp+arg_10], rbp
0x18000ecda  mov     [rsp+arg_0], rcx
0x18000ecdf  push    rsi
0x18000ece0  push    rdi
0x18000ece1  push    r15
0x18000ece3  sub     rsp, 20h
0x18000ece7  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000ecee  mov     rbx, rdx
0x18000ecf1  mov     qword ptr [rdx], 0
0x18000ecf8  mov     eax, [rsi]
0x18000ecfa  mov     [rdx], eax
0x18000ecfc  and     eax, 6
0x18000ecff  cmp     al, 6
0x18000ed01  jz      loc_18000EE27
0x18000ed07  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ed0c  mov     ebp, eax
0x18000ed0e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ed16  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ed1d  test    rax, rax
0x18000ed20  jz      short loc_18000ED3A
0x18000ed22  lea     r8, [rsp+38h+arg_0]
0x18000ed27  mov     edx, 3
0x18000ed2c  mov     ecx, 37E287Eh
0x18000ed31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed36  mov     edx, eax
0x18000ed38  jmp     short loc_18000ED48
0x18000ed3a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ed41  test    rax, rax
0x18000ed44  jnz     short loc_18000ED22
0x18000ed46  xor     edx, edx
0x18000ed48  mov     r8d, edx
0x18000ed4b  mov     eax, edx
0x18000ed4d  and     r8d, 0FFFFFF3Fh
0x18000ed54  and     edx, 80h
0x18000ed5a  mov     ecx, r8d
0x18000ed5d  mov     r15d, 40h ; '@'
0x18000ed63  and     ecx, 3
0x18000ed66  and     eax, r15d
0x18000ed69  shl     ecx, 2
0x18000ed6c  or      ecx, eax
0x18000ed6e  shl     ecx, 2
0x18000ed71  or      ecx, edx
0x18000ed73  lea     edi, ds:0[rcx*8]
0x18000ed7a  test    r8d, r8d
0x18000ed7d  jnz     short loc_18000ED84
0x18000ed7f  mov     eax, r15d
0x18000ed82  jmp     short loc_18000ED8E
0x18000ed84  xor     eax, eax
0x18000ed86  cmp     r8d, 2
0x18000ed8a  cmovz   eax, r15d
0x18000ed8e  or      edi, eax
0x18000ed90  mov     eax, [rbx]
0x18000ed92  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ed97  mov     edx, eax
0x18000ed99  mov     [rbx], eax
0x18000ed9b  jz      short loc_18000EDC7
0x18000ed9d  test    dl, 2
0x18000eda0  jnz     short loc_18000EDC7
0x18000eda2  xor     eax, edi
0x18000eda4  and     eax, 180h
0x18000eda9  xor     eax, edx
0x18000edab  mov     ecx, eax
0x18000edad  xor     ecx, edi
0x18000edaf  and     ecx, r15d
0x18000edb2  xor     ecx, eax
0x18000edb4  or      ecx, 1
0x18000edb7  mov     eax, ecx
0x18000edb9  xor     eax, edi
0x18000edbb  and     eax, 800h
0x18000edc0  xor     eax, ecx
0x18000edc2  or      eax, 2
0x18000edc5  mov     [rbx], eax
0x18000edc7  mov     r8d, edx
0x18000edca  mov     ecx, eax
0x18000edcc  and     r8d, 4
0x18000edd0  jnz     short loc_18000EDE1
0x18000edd2  xor     ecx, edi
0x18000edd4  and     ecx, 400h
0x18000edda  xor     ecx, eax
0x18000eddc  or      ecx, 4
0x18000eddf  mov     [rbx], ecx
0x18000ede1  mov     eax, edx
0x18000ede3  lock cmpxchg [rsi], ecx
0x18000ede7  jnz     short loc_18000ED92
0x18000ede9  test    r8d, r8d
0x18000edec  jnz     short loc_18000EDFE
0x18000edee  mov     r8d, ebp
0x18000edf1  mov     edx, 3
0x18000edf6  mov     rcx, rsi
0x18000edf9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000edfe  test    byte ptr [rbx], 2
0x18000ee01  jnz     short loc_18000EE27
0x18000ee03  mov     eax, [rbx]
0x18000ee05  xor     eax, edi
0x18000ee07  and     eax, 180h
0x18000ee0c  xor     eax, [rbx]
0x18000ee0e  mov     ecx, eax
0x18000ee10  xor     ecx, edi
0x18000ee12  and     ecx, r15d
0x18000ee15  xor     ecx, eax
0x18000ee17  or      ecx, 1
0x18000ee1a  mov     eax, ecx
0x18000ee1c  xor     eax, edi
0x18000ee1e  and     eax, 800h
0x18000ee23  xor     eax, ecx
0x18000ee25  mov     [rbx], eax
0x18000ee27  mov     rbp, [rsp+38h+arg_10]
0x18000ee2c  mov     rax, rbx
0x18000ee2f  mov     rbx, [rsp+38h+arg_8]
0x18000ee34  add     rsp, 20h
0x18000ee38  pop     r15
0x18000ee3a  pop     rdi
0x18000ee3b  pop     rsi
0x18000ee3c  retn
```
