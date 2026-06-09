# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140010858`
- end: `0x140010969`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400109c4`
- `0x140010c10`

## callees

- `0x140010858`
- `0x1400109c4`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // ebx
  __int16 CurrentFeatureEnabledState; // di
  int v8; // ebp
  unsigned int v9; // esi
  signed __int32 v10; // eax
  int v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+58h] [rbp+10h]

  v3 = 0;
  v12 = 0;
  v13 = a2;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  CurrentFeatureEnabledState = wil_details_GetCurrentFeatureEnabledState(a3, &v12);
  if ( *(_BYTE *)(a3 + 28) )
    v8 = v12;
  else
    v8 = v3 != 0 ? v12 : 0;
  while ( 1 )
  {
    LODWORD(v13) = v5;
    v9 = v5;
    if ( v8 )
    {
      LODWORD(v13) = v5;
      if ( (v5 & 2) == 0 )
      {
        v9 = CurrentFeatureEnabledState & 0x9C1 | v5 & 0xFFFFF63E | 2;
        LODWORD(v13) = v9;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v9 = v9 & 0xFFFFFBFF | CurrentFeatureEnabledState & 0x400 | 4;
      LODWORD(v13) = v9;
    }
    v10 = _InterlockedCompareExchange(a1, v9, v5);
    if ( v5 == v10 )
      break;
    v5 = v10;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v13) = CurrentFeatureEnabledState & 0x9C1 | v9 & 0xFFFFF63E;
  return v13;
}

```

## disassembly

```asm
0x140010858  mov     [rsp+arg_10], rbx
0x14001085d  mov     [rsp+arg_18], rbp
0x140010862  push    rsi
0x140010863  push    rdi
0x140010864  push    r12
0x140010866  push    r14
0x140010868  push    r15
0x14001086a  sub     rsp, 20h
0x14001086e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140010875  xor     r14d, r14d
0x140010878  mov     [rsp+48h+arg_0], r14d
0x14001087d  mov     r15, r8
0x140010880  mov     [rsp+48h+arg_8], rdx
0x140010885  mov     rbx, rdx
0x140010888  mov     r12, rcx
0x14001088b  test    rax, rax
0x14001088e  jz      short loc_140010898
0x140010890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010895  mov     r14d, eax
0x140010898  lea     rdx, [rsp+48h+arg_0]
0x14001089d  mov     rcx, r15
0x1400108a0  call    wil_details_GetCurrentFeatureEnabledState
0x1400108a5  cmp     byte ptr [r15+1Ch], 0
0x1400108aa  mov     rdi, rax
0x1400108ad  jnz     short loc_1400108BC
0x1400108af  mov     ecx, r14d
0x1400108b2  neg     ecx
0x1400108b4  sbb     ebp, ebp
0x1400108b6  and     ebp, [rsp+48h+arg_0]
0x1400108ba  jmp     short loc_1400108C0
0x1400108bc  mov     ebp, [rsp+48h+arg_0]
0x1400108c0  mov     dword ptr [rsp+48h+arg_8], ebx
0x1400108c4  mov     esi, ebx
0x1400108c6  test    ebp, ebp
0x1400108c8  jz      short loc_1400108E9
0x1400108ca  mov     dword ptr [rsp+48h+arg_8], ebx
0x1400108ce  test    bl, 2
0x1400108d1  jnz     short loc_1400108E9
0x1400108d3  and     esi, 0FFFFF63Eh
0x1400108d9  mov     eax, edi
0x1400108db  and     eax, 9C1h
0x1400108e0  or      esi, eax
0x1400108e2  or      esi, 2
0x1400108e5  mov     dword ptr [rsp+48h+arg_8], esi
0x1400108e9  mov     edx, ebx
0x1400108eb  and     edx, 4
0x1400108ee  jnz     short loc_140010909
0x1400108f0  mov     eax, esi
0x1400108f2  mov     ecx, edi
0x1400108f4  and     ecx, 400h
0x1400108fa  btr     eax, 0Ah
0x1400108fe  mov     esi, ecx
0x140010900  or      esi, eax
0x140010902  or      esi, 4
0x140010905  mov     dword ptr [rsp+48h+arg_8], esi
0x140010909  mov     eax, ebx
0x14001090b  lock cmpxchg [r12], esi
0x140010911  jz      short loc_140010917
0x140010913  mov     ebx, eax
0x140010915  jmp     short loc_1400108C0
0x140010917  test    edx, edx
0x140010919  jnz     short loc_140010937
0x14001091b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140010922  test    rax, rax
0x140010925  jz      short loc_140010937
0x140010927  movzx   edx, byte ptr [r15+1Ch]
0x14001092c  mov     r8d, r14d
0x14001092f  mov     rcx, r12
0x140010932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010937  test    ebp, ebp
0x140010939  jnz     short loc_14001094D
0x14001093b  and     esi, 0FFFFF63Eh
0x140010941  and     edi, 9C1h
0x140010947  or      esi, edi
0x140010949  mov     dword ptr [rsp+48h+arg_8], esi
0x14001094d  mov     rax, [rsp+48h+arg_8]
0x140010952  mov     rbx, [rsp+48h+arg_10]
0x140010957  mov     rbp, [rsp+48h+arg_18]
0x14001095c  add     rsp, 20h
0x140010960  pop     r15
0x140010962  pop     r14
0x140010964  pop     r12
0x140010966  pop     rdi
0x140010967  pop     rsi
0x140010968  retn
```
