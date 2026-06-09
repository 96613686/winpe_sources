# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000f040`
- end: `0x18000f152`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f158`
- `0x18002d67c`

## callees

- `0x18000f040`
- `0x18000f158`
- `0x180035010`

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
0x18000f040  mov     [rsp+arg_10], rbx
0x18000f045  mov     [rsp+arg_18], rbp
0x18000f04a  push    rsi
0x18000f04b  push    rdi
0x18000f04c  push    r12
0x18000f04e  push    r14
0x18000f050  push    r15
0x18000f052  sub     rsp, 20h
0x18000f056  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000f05d  xor     r14d, r14d
0x18000f060  mov     [rsp+48h+arg_0], r14d
0x18000f065  mov     r15, r8
0x18000f068  mov     [rsp+48h+arg_8], rdx
0x18000f06d  mov     rbx, rdx
0x18000f070  mov     r12, rcx
0x18000f073  test    rax, rax
0x18000f076  jz      short loc_18000F080
0x18000f078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f07d  mov     r14d, eax
0x18000f080  lea     rdx, [rsp+48h+arg_0]
0x18000f085  mov     rcx, r15
0x18000f088  call    wil_details_GetCurrentFeatureEnabledState
0x18000f08d  cmp     byte ptr [r15+1Ch], 0
0x18000f092  mov     rdi, rax
0x18000f095  jnz     short loc_18000F0A4
0x18000f097  mov     ecx, r14d
0x18000f09a  neg     ecx
0x18000f09c  sbb     ebp, ebp
0x18000f09e  and     ebp, [rsp+48h+arg_0]
0x18000f0a2  jmp     short loc_18000F0A8
0x18000f0a4  mov     ebp, [rsp+48h+arg_0]
0x18000f0a8  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000f0ac  mov     esi, ebx
0x18000f0ae  test    ebp, ebp
0x18000f0b0  jz      short loc_18000F0D1
0x18000f0b2  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000f0b6  test    bl, 2
0x18000f0b9  jnz     short loc_18000F0D1
0x18000f0bb  and     esi, 0FFFFF63Eh
0x18000f0c1  mov     eax, edi
0x18000f0c3  and     eax, 9C1h
0x18000f0c8  or      esi, eax
0x18000f0ca  or      esi, 2
0x18000f0cd  mov     dword ptr [rsp+48h+arg_8], esi
0x18000f0d1  mov     edx, ebx
0x18000f0d3  and     edx, 4
0x18000f0d6  jnz     short loc_18000F0F1
0x18000f0d8  mov     eax, esi
0x18000f0da  mov     ecx, edi
0x18000f0dc  and     ecx, 400h
0x18000f0e2  btr     eax, 0Ah
0x18000f0e6  mov     esi, ecx
0x18000f0e8  or      esi, eax
0x18000f0ea  or      esi, 4
0x18000f0ed  mov     dword ptr [rsp+48h+arg_8], esi
0x18000f0f1  mov     eax, ebx
0x18000f0f3  lock cmpxchg [r12], esi
0x18000f0f9  jz      short loc_18000F0FF
0x18000f0fb  mov     ebx, eax
0x18000f0fd  jmp     short loc_18000F0A8
0x18000f0ff  test    edx, edx
0x18000f101  jnz     short loc_18000F11F
0x18000f103  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000f10a  test    rax, rax
0x18000f10d  jz      short loc_18000F11F
0x18000f10f  movzx   edx, byte ptr [r15+1Ch]
0x18000f114  mov     r8d, r14d
0x18000f117  mov     rcx, r12
0x18000f11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f11f  test    ebp, ebp
0x18000f121  jnz     short loc_18000F135
0x18000f123  and     esi, 0FFFFF63Eh
0x18000f129  and     edi, 9C1h
0x18000f12f  or      esi, edi
0x18000f131  mov     dword ptr [rsp+48h+arg_8], esi
0x18000f135  mov     rax, [rsp+48h+arg_8]
0x18000f13a  mov     rbx, [rsp+48h+arg_10]
0x18000f13f  mov     rbp, [rsp+48h+arg_18]
0x18000f144  add     rsp, 20h
0x18000f148  pop     r15
0x18000f14a  pop     r14
0x18000f14c  pop     r12
0x18000f14e  pop     rdi
0x18000f14f  pop     rsi
0x18000f150  retn
```
