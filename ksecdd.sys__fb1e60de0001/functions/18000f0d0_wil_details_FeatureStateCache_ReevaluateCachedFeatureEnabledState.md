# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000f0d0`
- end: `0x18000f1e3`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eb94`
- `0x18000f348`

## callees

- `0x18000f0d0`
- `0x18000f230`
- `0x180010980`

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
0x18000f0d0  mov     [rsp+arg_10], rbx
0x18000f0d5  mov     [rsp+arg_18], rbp
0x18000f0da  push    rsi
0x18000f0db  push    rdi
0x18000f0dc  push    r12
0x18000f0de  push    r14
0x18000f0e0  push    r15
0x18000f0e2  sub     rsp, 20h
0x18000f0e6  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000f0ed  xor     r14d, r14d
0x18000f0f0  mov     [rsp+48h+arg_0], r14d
0x18000f0f5  mov     r15, r8
0x18000f0f8  mov     [rsp+48h+arg_8], rdx
0x18000f0fd  mov     rdi, rdx
0x18000f100  mov     r12, rcx
0x18000f103  test    rax, rax
0x18000f106  jz      short loc_18000F110
0x18000f108  call    _guard_dispatch_icall
0x18000f10d  mov     r14d, eax
0x18000f110  lea     rdx, [rsp+48h+arg_0]
0x18000f115  mov     rcx, r15
0x18000f118  call    wil_details_GetCurrentFeatureEnabledState
0x18000f11d  cmp     byte ptr [r15+1Ch], 0
0x18000f122  mov     rbx, rax
0x18000f125  jnz     short loc_18000F134
0x18000f127  mov     ecx, r14d
0x18000f12a  neg     ecx
0x18000f12c  sbb     ebp, ebp
0x18000f12e  and     ebp, [rsp+48h+arg_0]
0x18000f132  jmp     short loc_18000F138
0x18000f134  mov     ebp, [rsp+48h+arg_0]
0x18000f138  mov     dword ptr [rsp+48h+arg_8], edi
0x18000f13c  mov     esi, edi
0x18000f13e  test    ebp, ebp
0x18000f140  jz      short loc_18000F162
0x18000f142  mov     dword ptr [rsp+48h+arg_8], edi
0x18000f146  test    dil, 2
0x18000f14a  jnz     short loc_18000F162
0x18000f14c  and     esi, 0FFFFF63Eh
0x18000f152  mov     eax, ebx
0x18000f154  and     eax, 9C1h
0x18000f159  or      esi, eax
0x18000f15b  or      esi, 2
0x18000f15e  mov     dword ptr [rsp+48h+arg_8], esi
0x18000f162  mov     edx, edi
0x18000f164  and     edx, 4
0x18000f167  jnz     short loc_18000F182
0x18000f169  mov     eax, esi
0x18000f16b  mov     ecx, ebx
0x18000f16d  and     ecx, 400h
0x18000f173  btr     eax, 0Ah
0x18000f177  mov     esi, ecx
0x18000f179  or      esi, eax
0x18000f17b  or      esi, 4
0x18000f17e  mov     dword ptr [rsp+48h+arg_8], esi
0x18000f182  mov     eax, edi
0x18000f184  lock cmpxchg [r12], esi
0x18000f18a  jz      short loc_18000F190
0x18000f18c  mov     edi, eax
0x18000f18e  jmp     short loc_18000F138
0x18000f190  test    edx, edx
0x18000f192  jnz     short loc_18000F1B0
0x18000f194  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000f19b  test    rax, rax
0x18000f19e  jz      short loc_18000F1B0
0x18000f1a0  movzx   edx, byte ptr [r15+1Ch]
0x18000f1a5  mov     r8d, r14d
0x18000f1a8  mov     rcx, r12
0x18000f1ab  call    _guard_dispatch_icall
0x18000f1b0  test    ebp, ebp
0x18000f1b2  jnz     short loc_18000F1C6
0x18000f1b4  and     ebx, 9C1h
0x18000f1ba  and     esi, 0FFFFF63Eh
0x18000f1c0  or      ebx, esi
0x18000f1c2  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000f1c6  mov     rax, [rsp+48h+arg_8]
0x18000f1cb  mov     rbx, [rsp+48h+arg_10]
0x18000f1d0  mov     rbp, [rsp+48h+arg_18]
0x18000f1d5  add     rsp, 20h
0x18000f1d9  pop     r15
0x18000f1db  pop     r14
0x18000f1dd  pop     r12
0x18000f1df  pop     rdi
0x18000f1e0  pop     rsi
0x18000f1e1  retn
```
