# wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::GetCachedFeatureEnabledState(void)

- ea: `0x18001d678`
- end: `0x18001d811`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `409`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024c98`
- `0x180026404`

## callees

- `0x18001d144`
- `0x18001d678`
- `0x180025644`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebp
  __int64 (__fastcall *v7)(__int64, __int64, int *); // rax
  int v8; // edx
  int v9; // ebx
  int v10; // ebx
  int v11; // eax
  char v12; // cl
  int v13; // eax
  signed __int32 v14; // edx
  int v15; // ebx
  bool v16; // zf
  signed __int32 v17; // ecx
  signed __int32 v18; // eax
  int v19; // eax
  int v21; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v3 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v21 = 0;
  v6 = v5;
  v7 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v7 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v8 = v7(55623657, 3, &v21);
  }
  else
  {
    v8 = 0;
  }
  v9 = 8 * (v8 & 0x80 | (4 * (v8 & 0x40 | (4 * (v8 & 3)))));
  if ( (v8 & 0xFFFFFF3F) != 0 )
  {
    v11 = 0;
    if ( (v8 & 0xFFFFFF3F) == 2 )
      v11 = 64;
    v10 = v11 | v9;
  }
  else
  {
    v10 = v9 | 0x40;
  }
  v12 = 0;
  if ( (v10 & 0xC00) == 0xC00 )
  {
    v12 = 1;
  }
  else if ( (v10 & 0x40) != 0 )
  {
    goto LABEL_17;
  }
  if ( (v10 & 0x40) == 0 || !v12 )
  {
    v13 = 0;
    goto LABEL_18;
  }
LABEL_17:
  v13 = 1;
LABEL_18:
  v14 = *(_DWORD *)a2;
  v15 = v13 | v10;
  while ( 1 )
  {
    v16 = v21 == 0;
    v17 = v14;
    *(_DWORD *)a2 = v14;
    if ( !v16 && (v14 & 2) == 0 )
    {
      v17 = v14
          ^ ((unsigned __int16)v14
           ^ (unsigned __int16)v15)
          & 0x180
          ^ (v15
           ^ v14
           ^ ((unsigned __int16)v14
            ^ (unsigned __int16)v15)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v15
           ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80 ^ (v15 ^ v14 ^ (v14 ^ v15) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)(v14
                              ^ (v14
                               ^ v15)
                              & 0x180
                              ^ (v15
                               ^ v14
                               ^ (v14
                                ^ v15)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v15
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v15) & 0x80 ^ (v15 ^ v14 ^ (v14 ^ v15) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v17;
    }
    if ( (v14 & 4) == 0 )
    {
      v17 = ((unsigned __int16)v17 ^ (unsigned __int16)v15) & 0x400 ^ v17 | 4;
      *(_DWORD *)a2 = v17;
    }
    v18 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v17, v14);
    if ( v14 == v18 )
      break;
    v14 = v18;
  }
  if ( (v14 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(a1, 3, v6);
  if ( (*(_BYTE *)a2 & 2) == 0 )
  {
    v19 = *(_DWORD *)a2 ^ (*(_DWORD *)a2 ^ v15) & 0x180;
    *(_DWORD *)a2 = v19
                  ^ (v19
                   ^ v15)
                  & 0x40
                  ^ ((unsigned __int8)v15
                   ^ (unsigned __int8)(v19 ^ (v19 ^ v15) & 0x40))
                  & 1
                  ^ ((unsigned __int16)v15
                   ^ (unsigned __int16)(v19
                                      ^ (v19
                                       ^ v15)
                                      & 0x40
                                      ^ ((unsigned __int8)v15
                                       ^ (unsigned __int8)(v19 ^ (v19 ^ v15) & 0x40))
                                      & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18001d678  mov     [rsp+arg_8], rbx
0x18001d67d  mov     [rsp+arg_10], rbp
0x18001d682  push    rsi
0x18001d683  push    rdi
0x18001d684  push    r15
0x18001d686  sub     rsp, 20h
0x18001d68a  and     qword ptr [rdx], 0
0x18001d68e  mov     rdi, rdx
0x18001d691  mov     eax, [rcx]
0x18001d693  mov     rsi, rcx
0x18001d696  mov     [rdx], eax
0x18001d698  and     eax, 6
0x18001d69b  cmp     al, 6
0x18001d69d  jz      loc_18001D7FA
0x18001d6a3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001d6a8  and     [rsp+38h+arg_0], 0
0x18001d6ad  mov     ebp, eax
0x18001d6af  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001d6b6  test    rax, rax
0x18001d6b9  jz      short loc_18001D6D3
0x18001d6bb  lea     r8, [rsp+38h+arg_0]
0x18001d6c0  mov     edx, 3
0x18001d6c5  mov     ecx, 350BFE9h
0x18001d6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6cf  mov     edx, eax
0x18001d6d1  jmp     short loc_18001D6E1
0x18001d6d3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001d6da  test    rax, rax
0x18001d6dd  jnz     short loc_18001D6BB
0x18001d6df  xor     edx, edx
0x18001d6e1  mov     r8d, edx
0x18001d6e4  mov     eax, edx
0x18001d6e6  and     r8d, 0FFFFFF3Fh
0x18001d6ed  and     edx, 80h
0x18001d6f3  mov     ecx, r8d
0x18001d6f6  mov     r15d, 40h ; '@'
0x18001d6fc  and     ecx, 3
0x18001d6ff  and     eax, r15d
0x18001d702  shl     ecx, 2
0x18001d705  or      ecx, eax
0x18001d707  shl     ecx, 2
0x18001d70a  or      ecx, edx
0x18001d70c  lea     ebx, ds:0[rcx*8]
0x18001d713  test    r8d, r8d
0x18001d716  jnz     short loc_18001D71D
0x18001d718  or      ebx, r15d
0x18001d71b  jmp     short loc_18001D729
0x18001d71d  xor     eax, eax
0x18001d71f  cmp     r8d, 2
0x18001d723  cmovz   eax, r15d
0x18001d727  or      ebx, eax
0x18001d729  mov     edx, 0C00h
0x18001d72e  mov     eax, ebx
0x18001d730  and     eax, edx
0x18001d732  xor     cl, cl
0x18001d734  cmp     eax, edx
0x18001d736  jnz     short loc_18001D73C
0x18001d738  mov     cl, 1
0x18001d73a  jmp     short loc_18001D741
0x18001d73c  test    r15b, bl
0x18001d73f  jnz     short loc_18001D74E
0x18001d741  test    r15b, bl
0x18001d744  jz      short loc_18001D74A
0x18001d746  test    cl, cl
0x18001d748  jnz     short loc_18001D74E
0x18001d74a  xor     eax, eax
0x18001d74c  jmp     short loc_18001D753
0x18001d74e  mov     eax, 1
0x18001d753  mov     edx, [rdi]
0x18001d755  or      ebx, eax
0x18001d757  cmp     [rsp+38h+arg_0], 0
0x18001d75c  mov     ecx, edx
0x18001d75e  mov     [rdi], edx
0x18001d760  jz      short loc_18001D795
0x18001d762  test    dl, 2
0x18001d765  jnz     short loc_18001D795
0x18001d767  mov     eax, ebx
0x18001d769  xor     eax, edx
0x18001d76b  and     eax, 180h
0x18001d770  xor     eax, edx
0x18001d772  mov     ecx, eax
0x18001d774  xor     ecx, ebx
0x18001d776  and     ecx, r15d
0x18001d779  xor     ecx, eax
0x18001d77b  mov     eax, ecx
0x18001d77d  xor     eax, ebx
0x18001d77f  and     eax, 1
0x18001d782  xor     eax, ecx
0x18001d784  mov     ecx, eax
0x18001d786  xor     ecx, ebx
0x18001d788  and     ecx, 800h
0x18001d78e  xor     ecx, eax
0x18001d790  or      ecx, 2
0x18001d793  mov     [rdi], ecx
0x18001d795  test    dl, 4
0x18001d798  jnz     short loc_18001D7AA
0x18001d79a  mov     eax, ebx
0x18001d79c  xor     eax, ecx
0x18001d79e  and     eax, 400h
0x18001d7a3  xor     ecx, eax
0x18001d7a5  or      ecx, 4
0x18001d7a8  mov     [rdi], ecx
0x18001d7aa  mov     eax, edx
0x18001d7ac  lock cmpxchg [rsi], ecx
0x18001d7b0  jz      short loc_18001D7B6
0x18001d7b2  mov     edx, eax
0x18001d7b4  jmp     short loc_18001D757
0x18001d7b6  test    dl, 4
0x18001d7b9  jnz     short loc_18001D7CB
0x18001d7bb  mov     r8d, ebp
0x18001d7be  mov     edx, 3
0x18001d7c3  mov     rcx, rsi
0x18001d7c6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001d7cb  test    byte ptr [rdi], 2
0x18001d7ce  jnz     short loc_18001D7FA
0x18001d7d0  mov     eax, ebx
0x18001d7d2  mov     ecx, ebx
0x18001d7d4  xor     eax, [rdi]
0x18001d7d6  and     eax, 180h
0x18001d7db  xor     eax, [rdi]
0x18001d7dd  xor     ecx, eax
0x18001d7df  and     ecx, r15d
0x18001d7e2  xor     ecx, eax
0x18001d7e4  mov     edx, ecx
0x18001d7e6  xor     edx, ebx
0x18001d7e8  and     edx, 1
0x18001d7eb  xor     edx, ecx
0x18001d7ed  mov     eax, edx
0x18001d7ef  xor     eax, ebx
0x18001d7f1  and     eax, 800h
0x18001d7f6  xor     eax, edx
0x18001d7f8  mov     [rdi], eax
0x18001d7fa  mov     rbx, [rsp+38h+arg_8]
0x18001d7ff  mov     rax, rdi
0x18001d802  mov     rbp, [rsp+38h+arg_10]
0x18001d807  add     rsp, 20h
0x18001d80b  pop     r15
0x18001d80d  pop     rdi
0x18001d80e  pop     rsi
0x18001d80f  retn
```
