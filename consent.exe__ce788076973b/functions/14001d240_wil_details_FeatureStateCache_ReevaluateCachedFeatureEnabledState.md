# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14001d240`
- end: `0x14001d352`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001d05c`
- `0x14001d4b4`

## callees

- `0x14001d240`
- `0x14001d39c`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // edi
  __int16 CurrentFeatureEnabledState; // bx
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
    LODWORD(v13) = v9 & 0xFFFFF63E | CurrentFeatureEnabledState & 0x9C1;
  return v13;
}

```

## disassembly

```asm
0x14001d240  mov     [rsp+arg_10], rbx
0x14001d245  mov     [rsp+arg_18], rbp
0x14001d24a  push    rsi
0x14001d24b  push    rdi
0x14001d24c  push    r12
0x14001d24e  push    r14
0x14001d250  push    r15
0x14001d252  sub     rsp, 20h
0x14001d256  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14001d25d  xor     r14d, r14d
0x14001d260  mov     [rsp+48h+arg_0], r14d
0x14001d265  mov     r15, r8
0x14001d268  mov     [rsp+48h+arg_8], rdx
0x14001d26d  mov     rdi, rdx
0x14001d270  mov     r12, rcx
0x14001d273  test    rax, rax
0x14001d276  jz      short loc_14001D280
0x14001d278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d27d  mov     r14d, eax
0x14001d280  lea     rdx, [rsp+48h+arg_0]
0x14001d285  mov     rcx, r15
0x14001d288  call    wil_details_GetCurrentFeatureEnabledState
0x14001d28d  cmp     byte ptr [r15+1Ch], 0
0x14001d292  mov     rbx, rax
0x14001d295  jnz     short loc_14001D2A4
0x14001d297  mov     ecx, r14d
0x14001d29a  neg     ecx
0x14001d29c  sbb     ebp, ebp
0x14001d29e  and     ebp, [rsp+48h+arg_0]
0x14001d2a2  jmp     short loc_14001D2A8
0x14001d2a4  mov     ebp, [rsp+48h+arg_0]
0x14001d2a8  mov     dword ptr [rsp+48h+arg_8], edi
0x14001d2ac  mov     esi, edi
0x14001d2ae  test    ebp, ebp
0x14001d2b0  jz      short loc_14001D2D2
0x14001d2b2  mov     dword ptr [rsp+48h+arg_8], edi
0x14001d2b6  test    dil, 2
0x14001d2ba  jnz     short loc_14001D2D2
0x14001d2bc  and     esi, 0FFFFF63Eh
0x14001d2c2  mov     eax, ebx
0x14001d2c4  and     eax, 9C1h
0x14001d2c9  or      esi, eax
0x14001d2cb  or      esi, 2
0x14001d2ce  mov     dword ptr [rsp+48h+arg_8], esi
0x14001d2d2  mov     edx, edi
0x14001d2d4  and     edx, 4
0x14001d2d7  jnz     short loc_14001D2F2
0x14001d2d9  mov     eax, esi
0x14001d2db  mov     ecx, ebx
0x14001d2dd  and     ecx, 400h
0x14001d2e3  btr     eax, 0Ah
0x14001d2e7  mov     esi, ecx
0x14001d2e9  or      esi, eax
0x14001d2eb  or      esi, 4
0x14001d2ee  mov     dword ptr [rsp+48h+arg_8], esi
0x14001d2f2  mov     eax, edi
0x14001d2f4  lock cmpxchg [r12], esi
0x14001d2fa  jz      short loc_14001D300
0x14001d2fc  mov     edi, eax
0x14001d2fe  jmp     short loc_14001D2A8
0x14001d300  test    edx, edx
0x14001d302  jnz     short loc_14001D320
0x14001d304  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x14001d30b  test    rax, rax
0x14001d30e  jz      short loc_14001D320
0x14001d310  movzx   edx, byte ptr [r15+1Ch]
0x14001d315  mov     r8d, r14d
0x14001d318  mov     rcx, r12
0x14001d31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d320  test    ebp, ebp
0x14001d322  jnz     short loc_14001D336
0x14001d324  and     ebx, 9C1h
0x14001d32a  and     esi, 0FFFFF63Eh
0x14001d330  or      ebx, esi
0x14001d332  mov     dword ptr [rsp+48h+arg_8], ebx
0x14001d336  mov     rax, [rsp+48h+arg_8]
0x14001d33b  mov     rbx, [rsp+48h+arg_10]
0x14001d340  mov     rbp, [rsp+48h+arg_18]
0x14001d345  add     rsp, 20h
0x14001d349  pop     r15
0x14001d34b  pop     r14
0x14001d34d  pop     r12
0x14001d34f  pop     rdi
0x14001d350  pop     rsi
0x14001d351  retn
```
