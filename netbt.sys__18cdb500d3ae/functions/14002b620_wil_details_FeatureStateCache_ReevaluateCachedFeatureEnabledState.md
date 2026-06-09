# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14002b620`
- end: `0x14002b732`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002b0e8`
- `0x14002b8a8`

## callees

- `0x14002b620`
- `0x14002b790`
- `0x140030f80`

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
0x14002b620  mov     [rsp+arg_10], rbx
0x14002b625  mov     [rsp+arg_18], rbp
0x14002b62a  push    rsi
0x14002b62b  push    rdi
0x14002b62c  push    r12
0x14002b62e  push    r14
0x14002b630  push    r15
0x14002b632  sub     rsp, 20h
0x14002b636  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14002b63d  xor     r14d, r14d
0x14002b640  mov     [rsp+48h+arg_0], r14d
0x14002b645  mov     r15, r8
0x14002b648  mov     [rsp+48h+arg_8], rdx
0x14002b64d  mov     rbx, rdx
0x14002b650  mov     r12, rcx
0x14002b653  test    rax, rax
0x14002b656  jz      short loc_14002B660
0x14002b658  call    _guard_dispatch_icall
0x14002b65d  mov     r14d, eax
0x14002b660  lea     rdx, [rsp+48h+arg_0]
0x14002b665  mov     rcx, r15
0x14002b668  call    wil_details_GetCurrentFeatureEnabledState
0x14002b66d  cmp     byte ptr [r15+1Ch], 0
0x14002b672  mov     rdi, rax
0x14002b675  jnz     short loc_14002B684
0x14002b677  mov     ecx, r14d
0x14002b67a  neg     ecx
0x14002b67c  sbb     ebp, ebp
0x14002b67e  and     ebp, [rsp+48h+arg_0]
0x14002b682  jmp     short loc_14002B688
0x14002b684  mov     ebp, [rsp+48h+arg_0]
0x14002b688  mov     dword ptr [rsp+48h+arg_8], ebx
0x14002b68c  mov     esi, ebx
0x14002b68e  test    ebp, ebp
0x14002b690  jz      short loc_14002B6B1
0x14002b692  mov     dword ptr [rsp+48h+arg_8], ebx
0x14002b696  test    bl, 2
0x14002b699  jnz     short loc_14002B6B1
0x14002b69b  and     esi, 0FFFFF63Eh
0x14002b6a1  mov     eax, edi
0x14002b6a3  and     eax, 9C1h
0x14002b6a8  or      esi, eax
0x14002b6aa  or      esi, 2
0x14002b6ad  mov     dword ptr [rsp+48h+arg_8], esi
0x14002b6b1  mov     edx, ebx
0x14002b6b3  and     edx, 4
0x14002b6b6  jnz     short loc_14002B6D1
0x14002b6b8  mov     eax, esi
0x14002b6ba  mov     ecx, edi
0x14002b6bc  and     ecx, 400h
0x14002b6c2  btr     eax, 0Ah
0x14002b6c6  mov     esi, ecx
0x14002b6c8  or      esi, eax
0x14002b6ca  or      esi, 4
0x14002b6cd  mov     dword ptr [rsp+48h+arg_8], esi
0x14002b6d1  mov     eax, ebx
0x14002b6d3  lock cmpxchg [r12], esi
0x14002b6d9  jz      short loc_14002B6DF
0x14002b6db  mov     ebx, eax
0x14002b6dd  jmp     short loc_14002B688
0x14002b6df  test    edx, edx
0x14002b6e1  jnz     short loc_14002B6FF
0x14002b6e3  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x14002b6ea  test    rax, rax
0x14002b6ed  jz      short loc_14002B6FF
0x14002b6ef  movzx   edx, byte ptr [r15+1Ch]
0x14002b6f4  mov     r8d, r14d
0x14002b6f7  mov     rcx, r12
0x14002b6fa  call    _guard_dispatch_icall
0x14002b6ff  test    ebp, ebp
0x14002b701  jnz     short loc_14002B715
0x14002b703  and     esi, 0FFFFF63Eh
0x14002b709  and     edi, 9C1h
0x14002b70f  or      esi, edi
0x14002b711  mov     dword ptr [rsp+48h+arg_8], esi
0x14002b715  mov     rax, [rsp+48h+arg_8]
0x14002b71a  mov     rbx, [rsp+48h+arg_10]
0x14002b71f  mov     rbp, [rsp+48h+arg_18]
0x14002b724  add     rsp, 20h
0x14002b728  pop     r15
0x14002b72a  pop     r14
0x14002b72c  pop     r12
0x14002b72e  pop     rdi
0x14002b72f  pop     rsi
0x14002b730  retn
```
