# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000890c`
- end: `0x180008a1d`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008a68`
- `0x180008cb4`

## callees

- `0x18000890c`
- `0x180008a68`
- `0x18000e010`

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
0x18000890c  mov     [rsp+arg_10], rbx
0x180008911  mov     [rsp+arg_18], rbp
0x180008916  push    rsi
0x180008917  push    rdi
0x180008918  push    r12
0x18000891a  push    r14
0x18000891c  push    r15
0x18000891e  sub     rsp, 20h
0x180008922  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180008929  xor     r14d, r14d
0x18000892c  mov     [rsp+48h+arg_0], r14d
0x180008931  mov     r15, r8
0x180008934  mov     [rsp+48h+arg_8], rdx
0x180008939  mov     rbx, rdx
0x18000893c  mov     r12, rcx
0x18000893f  test    rax, rax
0x180008942  jz      short loc_18000894C
0x180008944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008949  mov     r14d, eax
0x18000894c  lea     rdx, [rsp+48h+arg_0]
0x180008951  mov     rcx, r15
0x180008954  call    wil_details_GetCurrentFeatureEnabledState
0x180008959  cmp     byte ptr [r15+1Ch], 0
0x18000895e  mov     rdi, rax
0x180008961  jnz     short loc_180008970
0x180008963  mov     ecx, r14d
0x180008966  neg     ecx
0x180008968  sbb     ebp, ebp
0x18000896a  and     ebp, [rsp+48h+arg_0]
0x18000896e  jmp     short loc_180008974
0x180008970  mov     ebp, [rsp+48h+arg_0]
0x180008974  mov     dword ptr [rsp+48h+arg_8], ebx
0x180008978  mov     esi, ebx
0x18000897a  test    ebp, ebp
0x18000897c  jz      short loc_18000899D
0x18000897e  mov     dword ptr [rsp+48h+arg_8], ebx
0x180008982  test    bl, 2
0x180008985  jnz     short loc_18000899D
0x180008987  and     esi, 0FFFFF63Eh
0x18000898d  mov     eax, edi
0x18000898f  and     eax, 9C1h
0x180008994  or      esi, eax
0x180008996  or      esi, 2
0x180008999  mov     dword ptr [rsp+48h+arg_8], esi
0x18000899d  mov     edx, ebx
0x18000899f  and     edx, 4
0x1800089a2  jnz     short loc_1800089BD
0x1800089a4  mov     eax, esi
0x1800089a6  mov     ecx, edi
0x1800089a8  and     ecx, 400h
0x1800089ae  btr     eax, 0Ah
0x1800089b2  mov     esi, ecx
0x1800089b4  or      esi, eax
0x1800089b6  or      esi, 4
0x1800089b9  mov     dword ptr [rsp+48h+arg_8], esi
0x1800089bd  mov     eax, ebx
0x1800089bf  lock cmpxchg [r12], esi
0x1800089c5  jz      short loc_1800089CB
0x1800089c7  mov     ebx, eax
0x1800089c9  jmp     short loc_180008974
0x1800089cb  test    edx, edx
0x1800089cd  jnz     short loc_1800089EB
0x1800089cf  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1800089d6  test    rax, rax
0x1800089d9  jz      short loc_1800089EB
0x1800089db  movzx   edx, byte ptr [r15+1Ch]
0x1800089e0  mov     r8d, r14d
0x1800089e3  mov     rcx, r12
0x1800089e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089eb  test    ebp, ebp
0x1800089ed  jnz     short loc_180008A01
0x1800089ef  and     esi, 0FFFFF63Eh
0x1800089f5  and     edi, 9C1h
0x1800089fb  or      esi, edi
0x1800089fd  mov     dword ptr [rsp+48h+arg_8], esi
0x180008a01  mov     rax, [rsp+48h+arg_8]
0x180008a06  mov     rbx, [rsp+48h+arg_10]
0x180008a0b  mov     rbp, [rsp+48h+arg_18]
0x180008a10  add     rsp, 20h
0x180008a14  pop     r15
0x180008a16  pop     r14
0x180008a18  pop     r12
0x180008a1a  pop     rdi
0x180008a1b  pop     rsi
0x180008a1c  retn
```
