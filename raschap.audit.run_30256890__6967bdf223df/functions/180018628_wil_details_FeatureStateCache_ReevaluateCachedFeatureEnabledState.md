# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180018628`
- end: `0x180018739`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018164`
- `0x1800188f0`

## callees

- `0x180018628`
- `0x180018794`
- `0x180027010`

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
0x180018628  mov     [rsp+arg_10], rbx
0x18001862d  mov     [rsp+arg_18], rbp
0x180018632  push    rsi
0x180018633  push    rdi
0x180018634  push    r12
0x180018636  push    r14
0x180018638  push    r15
0x18001863a  sub     rsp, 20h
0x18001863e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180018645  xor     r14d, r14d
0x180018648  mov     [rsp+48h+arg_0], r14d
0x18001864d  mov     r15, r8
0x180018650  mov     [rsp+48h+arg_8], rdx
0x180018655  mov     rbx, rdx
0x180018658  mov     r12, rcx
0x18001865b  test    rax, rax
0x18001865e  jz      short loc_180018668
0x180018660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018665  mov     r14d, eax
0x180018668  lea     rdx, [rsp+48h+arg_0]
0x18001866d  mov     rcx, r15
0x180018670  call    wil_details_GetCurrentFeatureEnabledState
0x180018675  cmp     byte ptr [r15+1Ch], 0
0x18001867a  mov     rdi, rax
0x18001867d  jnz     short loc_18001868C
0x18001867f  mov     ecx, r14d
0x180018682  neg     ecx
0x180018684  sbb     ebp, ebp
0x180018686  and     ebp, [rsp+48h+arg_0]
0x18001868a  jmp     short loc_180018690
0x18001868c  mov     ebp, [rsp+48h+arg_0]
0x180018690  mov     dword ptr [rsp+48h+arg_8], ebx
0x180018694  mov     esi, ebx
0x180018696  test    ebp, ebp
0x180018698  jz      short loc_1800186B9
0x18001869a  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001869e  test    bl, 2
0x1800186a1  jnz     short loc_1800186B9
0x1800186a3  and     esi, 0FFFFF63Eh
0x1800186a9  mov     eax, edi
0x1800186ab  and     eax, 9C1h
0x1800186b0  or      esi, eax
0x1800186b2  or      esi, 2
0x1800186b5  mov     dword ptr [rsp+48h+arg_8], esi
0x1800186b9  mov     edx, ebx
0x1800186bb  and     edx, 4
0x1800186be  jnz     short loc_1800186D9
0x1800186c0  mov     eax, esi
0x1800186c2  mov     ecx, edi
0x1800186c4  and     ecx, 400h
0x1800186ca  btr     eax, 0Ah
0x1800186ce  mov     esi, ecx
0x1800186d0  or      esi, eax
0x1800186d2  or      esi, 4
0x1800186d5  mov     dword ptr [rsp+48h+arg_8], esi
0x1800186d9  mov     eax, ebx
0x1800186db  lock cmpxchg [r12], esi
0x1800186e1  jz      short loc_1800186E7
0x1800186e3  mov     ebx, eax
0x1800186e5  jmp     short loc_180018690
0x1800186e7  test    edx, edx
0x1800186e9  jnz     short loc_180018707
0x1800186eb  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1800186f2  test    rax, rax
0x1800186f5  jz      short loc_180018707
0x1800186f7  movzx   edx, byte ptr [r15+1Ch]
0x1800186fc  mov     r8d, r14d
0x1800186ff  mov     rcx, r12
0x180018702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018707  test    ebp, ebp
0x180018709  jnz     short loc_18001871D
0x18001870b  and     esi, 0FFFFF63Eh
0x180018711  and     edi, 9C1h
0x180018717  or      esi, edi
0x180018719  mov     dword ptr [rsp+48h+arg_8], esi
0x18001871d  mov     rax, [rsp+48h+arg_8]
0x180018722  mov     rbx, [rsp+48h+arg_10]
0x180018727  mov     rbp, [rsp+48h+arg_18]
0x18001872c  add     rsp, 20h
0x180018730  pop     r15
0x180018732  pop     r14
0x180018734  pop     r12
0x180018736  pop     rdi
0x180018737  pop     rsi
0x180018738  retn
```
