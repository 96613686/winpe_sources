# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180014de0`
- end: `0x180014f11`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800164ac`
- `0x18001ba78`

## callees

- `0x180014de0`
- `0x180014f18`
- `0x180020010`

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
0x180014de0  mov     [rsp+arg_10], rbx
0x180014de5  mov     [rsp+arg_18], rbp
0x180014dea  push    rsi
0x180014deb  push    rdi
0x180014dec  push    r12
0x180014dee  push    r14
0x180014df0  push    r15
0x180014df2  sub     rsp, 20h
0x180014df6  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180014dfd  xor     r14d, r14d
0x180014e00  mov     [rsp+48h+arg_0], r14d
0x180014e05  mov     r15, r8
0x180014e08  mov     [rsp+48h+arg_8], rdx
0x180014e0d  mov     rbx, rdx
0x180014e10  mov     r12, rcx
0x180014e13  test    rax, rax
0x180014e16  jnz     loc_180014E9D
0x180014e1c  lea     rdx, [rsp+48h+arg_0]
0x180014e21  mov     rcx, r15
0x180014e24  call    wil_details_GetCurrentFeatureEnabledState
0x180014e29  cmp     byte ptr [r15+1Ch], 0
0x180014e2e  mov     rdi, rax
0x180014e31  jnz     short loc_180014E97
0x180014e33  mov     ecx, r14d
0x180014e36  neg     ecx
0x180014e38  sbb     ebp, ebp
0x180014e3a  and     ebp, [rsp+48h+arg_0]
0x180014e3e  mov     dword ptr [rsp+48h+arg_8], ebx
0x180014e42  mov     esi, ebx
0x180014e44  test    ebp, ebp
0x180014e46  jnz     short loc_180014EAA
0x180014e48  mov     edx, ebx
0x180014e4a  and     edx, 4
0x180014e4d  jz      short loc_180014ECE
0x180014e4f  mov     eax, ebx
0x180014e51  lock cmpxchg [r12], esi
0x180014e57  jnz     short loc_180014E93
0x180014e59  test    edx, edx
0x180014e5b  jz      loc_180014EEC
0x180014e61  test    ebp, ebp
0x180014e63  jnz     short loc_180014E77
0x180014e65  and     esi, 0FFFFF63Eh
0x180014e6b  and     edi, 9C1h
0x180014e71  or      esi, edi
0x180014e73  mov     dword ptr [rsp+48h+arg_8], esi
0x180014e77  mov     rax, [rsp+48h+arg_8]
0x180014e7c  mov     rbx, [rsp+48h+arg_10]
0x180014e81  mov     rbp, [rsp+48h+arg_18]
0x180014e86  add     rsp, 20h
0x180014e8a  pop     r15
0x180014e8c  pop     r14
0x180014e8e  pop     r12
0x180014e90  pop     rdi
0x180014e91  pop     rsi
0x180014e92  retn
0x180014e93  mov     ebx, eax
0x180014e95  jmp     short loc_180014E3E
0x180014e97  mov     ebp, [rsp+48h+arg_0]
0x180014e9b  jmp     short loc_180014E3E
0x180014e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ea2  mov     r14d, eax
0x180014ea5  jmp     loc_180014E1C
0x180014eaa  mov     dword ptr [rsp+48h+arg_8], ebx
0x180014eae  test    bl, 2
0x180014eb1  jnz     short loc_180014E48
0x180014eb3  and     esi, 0FFFFF63Eh
0x180014eb9  mov     eax, edi
0x180014ebb  and     eax, 9C1h
0x180014ec0  or      esi, eax
0x180014ec2  or      esi, 2
0x180014ec5  mov     dword ptr [rsp+48h+arg_8], esi
0x180014ec9  jmp     loc_180014E48
0x180014ece  mov     eax, esi
0x180014ed0  mov     ecx, edi
0x180014ed2  and     ecx, 400h
0x180014ed8  btr     eax, 0Ah
0x180014edc  mov     esi, ecx
0x180014ede  or      esi, eax
0x180014ee0  or      esi, 4
0x180014ee3  mov     dword ptr [rsp+48h+arg_8], esi
0x180014ee7  jmp     loc_180014E4F
0x180014eec  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180014ef3  test    rax, rax
0x180014ef6  jz      loc_180014E61
0x180014efc  movzx   edx, byte ptr [r15+1Ch]
0x180014f01  mov     r8d, r14d
0x180014f04  mov     rcx, r12
0x180014f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f0c  jmp     loc_180014E61
```
