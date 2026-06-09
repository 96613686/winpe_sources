# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180014a90`
- end: `0x180014ba1`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014bfc`
- `0x180014e48`

## callees

- `0x180014a90`
- `0x180014bfc`
- `0x18001a010`

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
0x180014a90  mov     [rsp+arg_10], rbx
0x180014a95  mov     [rsp+arg_18], rbp
0x180014a9a  push    rsi
0x180014a9b  push    rdi
0x180014a9c  push    r12
0x180014a9e  push    r14
0x180014aa0  push    r15
0x180014aa2  sub     rsp, 20h
0x180014aa6  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180014aad  xor     r14d, r14d
0x180014ab0  mov     [rsp+48h+arg_0], r14d
0x180014ab5  mov     r15, r8
0x180014ab8  mov     [rsp+48h+arg_8], rdx
0x180014abd  mov     rbx, rdx
0x180014ac0  mov     r12, rcx
0x180014ac3  test    rax, rax
0x180014ac6  jz      short loc_180014AD0
0x180014ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014acd  mov     r14d, eax
0x180014ad0  lea     rdx, [rsp+48h+arg_0]
0x180014ad5  mov     rcx, r15
0x180014ad8  call    wil_details_GetCurrentFeatureEnabledState
0x180014add  cmp     byte ptr [r15+1Ch], 0
0x180014ae2  mov     rdi, rax
0x180014ae5  jnz     short loc_180014AF4
0x180014ae7  mov     ecx, r14d
0x180014aea  neg     ecx
0x180014aec  sbb     ebp, ebp
0x180014aee  and     ebp, [rsp+48h+arg_0]
0x180014af2  jmp     short loc_180014AF8
0x180014af4  mov     ebp, [rsp+48h+arg_0]
0x180014af8  mov     dword ptr [rsp+48h+arg_8], ebx
0x180014afc  mov     esi, ebx
0x180014afe  test    ebp, ebp
0x180014b00  jz      short loc_180014B21
0x180014b02  mov     dword ptr [rsp+48h+arg_8], ebx
0x180014b06  test    bl, 2
0x180014b09  jnz     short loc_180014B21
0x180014b0b  and     esi, 0FFFFF63Eh
0x180014b11  mov     eax, edi
0x180014b13  and     eax, 9C1h
0x180014b18  or      esi, eax
0x180014b1a  or      esi, 2
0x180014b1d  mov     dword ptr [rsp+48h+arg_8], esi
0x180014b21  mov     edx, ebx
0x180014b23  and     edx, 4
0x180014b26  jnz     short loc_180014B41
0x180014b28  mov     eax, esi
0x180014b2a  mov     ecx, edi
0x180014b2c  and     ecx, 400h
0x180014b32  btr     eax, 0Ah
0x180014b36  mov     esi, ecx
0x180014b38  or      esi, eax
0x180014b3a  or      esi, 4
0x180014b3d  mov     dword ptr [rsp+48h+arg_8], esi
0x180014b41  mov     eax, ebx
0x180014b43  lock cmpxchg [r12], esi
0x180014b49  jz      short loc_180014B4F
0x180014b4b  mov     ebx, eax
0x180014b4d  jmp     short loc_180014AF8
0x180014b4f  test    edx, edx
0x180014b51  jnz     short loc_180014B6F
0x180014b53  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180014b5a  test    rax, rax
0x180014b5d  jz      short loc_180014B6F
0x180014b5f  movzx   edx, byte ptr [r15+1Ch]
0x180014b64  mov     r8d, r14d
0x180014b67  mov     rcx, r12
0x180014b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b6f  test    ebp, ebp
0x180014b71  jnz     short loc_180014B85
0x180014b73  and     esi, 0FFFFF63Eh
0x180014b79  and     edi, 9C1h
0x180014b7f  or      esi, edi
0x180014b81  mov     dword ptr [rsp+48h+arg_8], esi
0x180014b85  mov     rax, [rsp+48h+arg_8]
0x180014b8a  mov     rbx, [rsp+48h+arg_10]
0x180014b8f  mov     rbp, [rsp+48h+arg_18]
0x180014b94  add     rsp, 20h
0x180014b98  pop     r15
0x180014b9a  pop     r14
0x180014b9c  pop     r12
0x180014b9e  pop     rdi
0x180014b9f  pop     rsi
0x180014ba0  retn
```
