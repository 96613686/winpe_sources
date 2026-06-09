# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180022e98`
- end: `0x180022faa`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023004`
- `0x1800231a0`

## callees

- `0x180022e98`
- `0x180023004`
- `0x180028010`

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
0x180022e98  mov     [rsp+arg_10], rbx
0x180022e9d  mov     [rsp+arg_18], rbp
0x180022ea2  push    rsi
0x180022ea3  push    rdi
0x180022ea4  push    r12
0x180022ea6  push    r14
0x180022ea8  push    r15
0x180022eaa  sub     rsp, 20h
0x180022eae  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180022eb5  xor     r14d, r14d
0x180022eb8  mov     [rsp+48h+arg_0], r14d
0x180022ebd  mov     r15, r8
0x180022ec0  mov     [rsp+48h+arg_8], rdx
0x180022ec5  mov     rbx, rdx
0x180022ec8  mov     r12, rcx
0x180022ecb  test    rax, rax
0x180022ece  jz      short loc_180022ED8
0x180022ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ed5  mov     r14d, eax
0x180022ed8  lea     rdx, [rsp+48h+arg_0]
0x180022edd  mov     rcx, r15
0x180022ee0  call    wil_details_GetCurrentFeatureEnabledState
0x180022ee5  cmp     byte ptr [r15+1Ch], 0
0x180022eea  mov     rdi, rax
0x180022eed  jnz     short loc_180022EFC
0x180022eef  mov     ecx, r14d
0x180022ef2  neg     ecx
0x180022ef4  sbb     ebp, ebp
0x180022ef6  and     ebp, [rsp+48h+arg_0]
0x180022efa  jmp     short loc_180022F00
0x180022efc  mov     ebp, [rsp+48h+arg_0]
0x180022f00  mov     dword ptr [rsp+48h+arg_8], ebx
0x180022f04  mov     esi, ebx
0x180022f06  test    ebp, ebp
0x180022f08  jz      short loc_180022F29
0x180022f0a  mov     dword ptr [rsp+48h+arg_8], ebx
0x180022f0e  test    bl, 2
0x180022f11  jnz     short loc_180022F29
0x180022f13  and     esi, 0FFFFF63Eh
0x180022f19  mov     eax, edi
0x180022f1b  and     eax, 9C1h
0x180022f20  or      esi, eax
0x180022f22  or      esi, 2
0x180022f25  mov     dword ptr [rsp+48h+arg_8], esi
0x180022f29  mov     edx, ebx
0x180022f2b  and     edx, 4
0x180022f2e  jnz     short loc_180022F49
0x180022f30  mov     eax, esi
0x180022f32  mov     ecx, edi
0x180022f34  and     ecx, 400h
0x180022f3a  btr     eax, 0Ah
0x180022f3e  mov     esi, ecx
0x180022f40  or      esi, eax
0x180022f42  or      esi, 4
0x180022f45  mov     dword ptr [rsp+48h+arg_8], esi
0x180022f49  mov     eax, ebx
0x180022f4b  lock cmpxchg [r12], esi
0x180022f51  jz      short loc_180022F57
0x180022f53  mov     ebx, eax
0x180022f55  jmp     short loc_180022F00
0x180022f57  test    edx, edx
0x180022f59  jnz     short loc_180022F77
0x180022f5b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180022f62  test    rax, rax
0x180022f65  jz      short loc_180022F77
0x180022f67  movzx   edx, byte ptr [r15+1Ch]
0x180022f6c  mov     r8d, r14d
0x180022f6f  mov     rcx, r12
0x180022f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f77  test    ebp, ebp
0x180022f79  jnz     short loc_180022F8D
0x180022f7b  and     esi, 0FFFFF63Eh
0x180022f81  and     edi, 9C1h
0x180022f87  or      esi, edi
0x180022f89  mov     dword ptr [rsp+48h+arg_8], esi
0x180022f8d  mov     rax, [rsp+48h+arg_8]
0x180022f92  mov     rbx, [rsp+48h+arg_10]
0x180022f97  mov     rbp, [rsp+48h+arg_18]
0x180022f9c  add     rsp, 20h
0x180022fa0  pop     r15
0x180022fa2  pop     r14
0x180022fa4  pop     r12
0x180022fa6  pop     rdi
0x180022fa7  pop     rsi
0x180022fa8  retn
```
