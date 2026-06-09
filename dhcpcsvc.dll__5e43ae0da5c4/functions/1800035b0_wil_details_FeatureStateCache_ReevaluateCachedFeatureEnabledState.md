# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x1800035b0`
- end: `0x1800036c1`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003530`
- `0x180010640`

## callees

- `0x1800035b0`
- `0x1800036c8`
- `0x180014010`

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
0x1800035b0  mov     [rsp+arg_10], rbx
0x1800035b5  mov     [rsp+arg_18], rbp
0x1800035ba  push    rsi
0x1800035bb  push    rdi
0x1800035bc  push    r12
0x1800035be  push    r14
0x1800035c0  push    r15
0x1800035c2  sub     rsp, 20h
0x1800035c6  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x1800035cd  xor     r14d, r14d
0x1800035d0  mov     [rsp+48h+arg_0], r14d
0x1800035d5  mov     r15, r8
0x1800035d8  mov     [rsp+48h+arg_8], rdx
0x1800035dd  mov     rbx, rdx
0x1800035e0  mov     r12, rcx
0x1800035e3  test    rax, rax
0x1800035e6  jz      short loc_1800035F0
0x1800035e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ed  mov     r14d, eax
0x1800035f0  lea     rdx, [rsp+48h+arg_0]
0x1800035f5  mov     rcx, r15
0x1800035f8  call    wil_details_GetCurrentFeatureEnabledState
0x1800035fd  cmp     byte ptr [r15+1Ch], 0
0x180003602  mov     rdi, rax
0x180003605  jnz     short loc_180003614
0x180003607  mov     ecx, r14d
0x18000360a  neg     ecx
0x18000360c  sbb     ebp, ebp
0x18000360e  and     ebp, [rsp+48h+arg_0]
0x180003612  jmp     short loc_180003618
0x180003614  mov     ebp, [rsp+48h+arg_0]
0x180003618  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000361c  mov     esi, ebx
0x18000361e  test    ebp, ebp
0x180003620  jz      short loc_180003641
0x180003622  mov     dword ptr [rsp+48h+arg_8], ebx
0x180003626  test    bl, 2
0x180003629  jnz     short loc_180003641
0x18000362b  and     esi, 0FFFFF63Eh
0x180003631  mov     eax, edi
0x180003633  and     eax, 9C1h
0x180003638  or      esi, eax
0x18000363a  or      esi, 2
0x18000363d  mov     dword ptr [rsp+48h+arg_8], esi
0x180003641  mov     edx, ebx
0x180003643  and     edx, 4
0x180003646  jnz     short loc_180003661
0x180003648  mov     eax, esi
0x18000364a  mov     ecx, edi
0x18000364c  and     ecx, 400h
0x180003652  btr     eax, 0Ah
0x180003656  mov     esi, ecx
0x180003658  or      esi, eax
0x18000365a  or      esi, 4
0x18000365d  mov     dword ptr [rsp+48h+arg_8], esi
0x180003661  mov     eax, ebx
0x180003663  lock cmpxchg [r12], esi
0x180003669  jz      short loc_18000366F
0x18000366b  mov     ebx, eax
0x18000366d  jmp     short loc_180003618
0x18000366f  test    edx, edx
0x180003671  jnz     short loc_18000368F
0x180003673  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000367a  test    rax, rax
0x18000367d  jz      short loc_18000368F
0x18000367f  movzx   edx, byte ptr [r15+1Ch]
0x180003684  mov     r8d, r14d
0x180003687  mov     rcx, r12
0x18000368a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000368f  test    ebp, ebp
0x180003691  jnz     short loc_1800036A5
0x180003693  and     esi, 0FFFFF63Eh
0x180003699  and     edi, 9C1h
0x18000369f  or      esi, edi
0x1800036a1  mov     dword ptr [rsp+48h+arg_8], esi
0x1800036a5  mov     rax, [rsp+48h+arg_8]
0x1800036aa  mov     rbx, [rsp+48h+arg_10]
0x1800036af  mov     rbp, [rsp+48h+arg_18]
0x1800036b4  add     rsp, 20h
0x1800036b8  pop     r15
0x1800036ba  pop     r14
0x1800036bc  pop     r12
0x1800036be  pop     rdi
0x1800036bf  pop     rsi
0x1800036c0  retn
```
