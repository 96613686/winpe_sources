# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180002760`
- end: `0x180002871`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800026e0`
- `0x180002880`

## callees

- `0x180002760`
- `0x180002880`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r12d
  signed __int32 v5; // ebx
  __int16 CurrentFeatureEnabledState; // di
  int v8; // ebp
  unsigned int v9; // r14d
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
  v8 = v12;
  if ( !*(_BYTE *)(a3 + 28) && !v3 )
    v8 = 0;
  while ( 1 )
  {
    LODWORD(v13) = v5;
    v9 = v5;
    if ( v8 && (v5 & 2) == 0 )
    {
      v9 = CurrentFeatureEnabledState & 0x9C1 | v5 & 0xFFFFF63E | 2;
      LODWORD(v13) = v9;
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
0x180002760  mov     [rsp+arg_10], rbx
0x180002765  mov     [rsp+arg_18], rbp
0x18000276a  push    rsi
0x18000276b  push    rdi
0x18000276c  push    r12
0x18000276e  push    r14
0x180002770  push    r15
0x180002772  sub     rsp, 20h
0x180002776  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000277d  xor     r12d, r12d
0x180002780  mov     [rsp+48h+arg_0], r12d
0x180002785  mov     rsi, r8
0x180002788  mov     [rsp+48h+arg_8], rdx
0x18000278d  mov     rbx, rdx
0x180002790  mov     r15, rcx
0x180002793  test    rax, rax
0x180002796  jz      short loc_1800027A0
0x180002798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000279d  mov     r12d, eax
0x1800027a0  lea     rdx, [rsp+48h+arg_0]
0x1800027a5  mov     rcx, rsi
0x1800027a8  call    wil_details_GetCurrentFeatureEnabledState
0x1800027ad  cmp     byte ptr [rsi+1Ch], 0
0x1800027b1  mov     rdi, rax
0x1800027b4  mov     ebp, [rsp+48h+arg_0]
0x1800027b8  jnz     short loc_1800027C2
0x1800027ba  xor     ecx, ecx
0x1800027bc  test    r12d, r12d
0x1800027bf  cmovz   ebp, ecx
0x1800027c2  mov     dword ptr [rsp+48h+arg_8], ebx
0x1800027c6  mov     r14d, ebx
0x1800027c9  test    ebp, ebp
0x1800027cb  jz      short loc_1800027EC
0x1800027cd  test    bl, 2
0x1800027d0  jnz     short loc_1800027EC
0x1800027d2  and     r14d, 0FFFFF63Eh
0x1800027d9  mov     eax, edi
0x1800027db  and     eax, 9C1h
0x1800027e0  or      r14d, eax
0x1800027e3  or      r14d, 2
0x1800027e7  mov     dword ptr [rsp+48h+arg_8], r14d
0x1800027ec  test    bl, 4
0x1800027ef  jnz     short loc_18000280F
0x1800027f1  mov     eax, r14d
0x1800027f4  mov     ecx, edi
0x1800027f6  and     ecx, 400h
0x1800027fc  btr     eax, 0Ah
0x180002800  mov     r14d, ecx
0x180002803  or      r14d, eax
0x180002806  or      r14d, 4
0x18000280a  mov     dword ptr [rsp+48h+arg_8], r14d
0x18000280f  mov     eax, ebx
0x180002811  lock cmpxchg [r15], r14d
0x180002816  jz      short loc_18000281C
0x180002818  mov     ebx, eax
0x18000281a  jmp     short loc_1800027C2
0x18000281c  test    bl, 4
0x18000281f  jnz     short loc_18000283C
0x180002821  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180002828  test    rax, rax
0x18000282b  jz      short loc_18000283C
0x18000282d  movzx   edx, byte ptr [rsi+1Ch]
0x180002831  mov     r8d, r12d
0x180002834  mov     rcx, r15
0x180002837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283c  test    ebp, ebp
0x18000283e  jnz     short loc_180002855
0x180002840  and     r14d, 0FFFFF63Eh
0x180002847  and     edi, 9C1h
0x18000284d  or      r14d, edi
0x180002850  mov     dword ptr [rsp+48h+arg_8], r14d
0x180002855  mov     rax, [rsp+48h+arg_8]
0x18000285a  mov     rbx, [rsp+48h+arg_10]
0x18000285f  mov     rbp, [rsp+48h+arg_18]
0x180002864  add     rsp, 20h
0x180002868  pop     r15
0x18000286a  pop     r14
0x18000286c  pop     r12
0x18000286e  pop     rdi
0x18000286f  pop     rsi
0x180002870  retn
```
