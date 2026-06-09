# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x1400285ac`
- end: `0x1400286be`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028044`
- `0x140028820`

## callees

- `0x1400285ac`
- `0x140028708`
- `0x14003e470`

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
0x1400285ac  mov     [rsp+arg_10], rbx
0x1400285b1  mov     [rsp+arg_18], rbp
0x1400285b6  push    rsi
0x1400285b7  push    rdi
0x1400285b8  push    r12
0x1400285ba  push    r14
0x1400285bc  push    r15
0x1400285be  sub     rsp, 20h
0x1400285c2  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x1400285c9  xor     r14d, r14d
0x1400285cc  mov     [rsp+48h+arg_0], r14d
0x1400285d1  mov     r15, r8
0x1400285d4  mov     [rsp+48h+arg_8], rdx
0x1400285d9  mov     rbx, rdx
0x1400285dc  mov     r12, rcx
0x1400285df  test    rax, rax
0x1400285e2  jz      short loc_1400285EC
0x1400285e4  call    _guard_dispatch_icall
0x1400285e9  mov     r14d, eax
0x1400285ec  lea     rdx, [rsp+48h+arg_0]
0x1400285f1  mov     rcx, r15
0x1400285f4  call    wil_details_GetCurrentFeatureEnabledState
0x1400285f9  cmp     byte ptr [r15+1Ch], 0
0x1400285fe  mov     rdi, rax
0x140028601  jnz     short loc_140028610
0x140028603  mov     ecx, r14d
0x140028606  neg     ecx
0x140028608  sbb     ebp, ebp
0x14002860a  and     ebp, [rsp+48h+arg_0]
0x14002860e  jmp     short loc_140028614
0x140028610  mov     ebp, [rsp+48h+arg_0]
0x140028614  mov     dword ptr [rsp+48h+arg_8], ebx
0x140028618  mov     esi, ebx
0x14002861a  test    ebp, ebp
0x14002861c  jz      short loc_14002863D
0x14002861e  mov     dword ptr [rsp+48h+arg_8], ebx
0x140028622  test    bl, 2
0x140028625  jnz     short loc_14002863D
0x140028627  and     esi, 0FFFFF63Eh
0x14002862d  mov     eax, edi
0x14002862f  and     eax, 9C1h
0x140028634  or      esi, eax
0x140028636  or      esi, 2
0x140028639  mov     dword ptr [rsp+48h+arg_8], esi
0x14002863d  mov     edx, ebx
0x14002863f  and     edx, 4
0x140028642  jnz     short loc_14002865D
0x140028644  mov     eax, esi
0x140028646  mov     ecx, edi
0x140028648  and     ecx, 400h
0x14002864e  btr     eax, 0Ah
0x140028652  mov     esi, ecx
0x140028654  or      esi, eax
0x140028656  or      esi, 4
0x140028659  mov     dword ptr [rsp+48h+arg_8], esi
0x14002865d  mov     eax, ebx
0x14002865f  lock cmpxchg [r12], esi
0x140028665  jz      short loc_14002866B
0x140028667  mov     ebx, eax
0x140028669  jmp     short loc_140028614
0x14002866b  test    edx, edx
0x14002866d  jnz     short loc_14002868B
0x14002866f  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140028676  test    rax, rax
0x140028679  jz      short loc_14002868B
0x14002867b  movzx   edx, byte ptr [r15+1Ch]
0x140028680  mov     r8d, r14d
0x140028683  mov     rcx, r12
0x140028686  call    _guard_dispatch_icall
0x14002868b  test    ebp, ebp
0x14002868d  jnz     short loc_1400286A1
0x14002868f  and     esi, 0FFFFF63Eh
0x140028695  and     edi, 9C1h
0x14002869b  or      esi, edi
0x14002869d  mov     dword ptr [rsp+48h+arg_8], esi
0x1400286a1  mov     rax, [rsp+48h+arg_8]
0x1400286a6  mov     rbx, [rsp+48h+arg_10]
0x1400286ab  mov     rbp, [rsp+48h+arg_18]
0x1400286b0  add     rsp, 20h
0x1400286b4  pop     r15
0x1400286b6  pop     r14
0x1400286b8  pop     r12
0x1400286ba  pop     rdi
0x1400286bb  pop     rsi
0x1400286bc  retn
```
