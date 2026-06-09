# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140002bd8`
- end: `0x140002cea`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001b8c`
- `0x1400026a0`

## callees

- `0x140002bd8`
- `0x140002d44`
- `0x140006010`

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
0x140002bd8  mov     [rsp+arg_10], rbx
0x140002bdd  mov     [rsp+arg_18], rbp
0x140002be2  push    rsi
0x140002be3  push    rdi
0x140002be4  push    r12
0x140002be6  push    r14
0x140002be8  push    r15
0x140002bea  sub     rsp, 20h
0x140002bee  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140002bf5  xor     r14d, r14d
0x140002bf8  mov     [rsp+48h+arg_0], r14d
0x140002bfd  mov     r15, r8
0x140002c00  mov     [rsp+48h+arg_8], rdx
0x140002c05  mov     rbx, rdx
0x140002c08  mov     r12, rcx
0x140002c0b  test    rax, rax
0x140002c0e  jz      short loc_140002C18
0x140002c10  call    _guard_dispatch_icall
0x140002c15  mov     r14d, eax
0x140002c18  lea     rdx, [rsp+48h+arg_0]
0x140002c1d  mov     rcx, r15
0x140002c20  call    wil_details_GetCurrentFeatureEnabledState
0x140002c25  cmp     byte ptr [r15+1Ch], 0
0x140002c2a  mov     rdi, rax
0x140002c2d  jnz     short loc_140002C3C
0x140002c2f  mov     ecx, r14d
0x140002c32  neg     ecx
0x140002c34  sbb     ebp, ebp
0x140002c36  and     ebp, [rsp+48h+arg_0]
0x140002c3a  jmp     short loc_140002C40
0x140002c3c  mov     ebp, [rsp+48h+arg_0]
0x140002c40  mov     dword ptr [rsp+48h+arg_8], ebx
0x140002c44  mov     esi, ebx
0x140002c46  test    ebp, ebp
0x140002c48  jz      short loc_140002C69
0x140002c4a  mov     dword ptr [rsp+48h+arg_8], ebx
0x140002c4e  test    bl, 2
0x140002c51  jnz     short loc_140002C69
0x140002c53  and     esi, 0FFFFF63Eh
0x140002c59  mov     eax, edi
0x140002c5b  and     eax, 9C1h
0x140002c60  or      esi, eax
0x140002c62  or      esi, 2
0x140002c65  mov     dword ptr [rsp+48h+arg_8], esi
0x140002c69  mov     edx, ebx
0x140002c6b  and     edx, 4
0x140002c6e  jnz     short loc_140002C89
0x140002c70  mov     eax, esi
0x140002c72  mov     ecx, edi
0x140002c74  and     ecx, 400h
0x140002c7a  btr     eax, 0Ah
0x140002c7e  mov     esi, ecx
0x140002c80  or      esi, eax
0x140002c82  or      esi, 4
0x140002c85  mov     dword ptr [rsp+48h+arg_8], esi
0x140002c89  mov     eax, ebx
0x140002c8b  lock cmpxchg [r12], esi
0x140002c91  jz      short loc_140002C97
0x140002c93  mov     ebx, eax
0x140002c95  jmp     short loc_140002C40
0x140002c97  test    edx, edx
0x140002c99  jnz     short loc_140002CB7
0x140002c9b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140002ca2  test    rax, rax
0x140002ca5  jz      short loc_140002CB7
0x140002ca7  movzx   edx, byte ptr [r15+1Ch]
0x140002cac  mov     r8d, r14d
0x140002caf  mov     rcx, r12
0x140002cb2  call    _guard_dispatch_icall
0x140002cb7  test    ebp, ebp
0x140002cb9  jnz     short loc_140002CCD
0x140002cbb  and     esi, 0FFFFF63Eh
0x140002cc1  and     edi, 9C1h
0x140002cc7  or      esi, edi
0x140002cc9  mov     dword ptr [rsp+48h+arg_8], esi
0x140002ccd  mov     rax, [rsp+48h+arg_8]
0x140002cd2  mov     rbx, [rsp+48h+arg_10]
0x140002cd7  mov     rbp, [rsp+48h+arg_18]
0x140002cdc  add     rsp, 20h
0x140002ce0  pop     r15
0x140002ce2  pop     r14
0x140002ce4  pop     r12
0x140002ce6  pop     rdi
0x140002ce7  pop     rsi
0x140002ce8  retn
```
